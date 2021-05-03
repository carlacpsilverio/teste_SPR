# teste_SPR
SPR
PennController.ResetPrefix(null);
PennController.DebugOff();
Sequence("Abertura","Pergunta1","Pergunta2","Pergunta3","Pergunta4","Pergunta5","Pergunta5","Pergunta6","Orientação","telatreino","Treino","start","sentenças", randomize("item"),SendResults(),"final");

newTrial("Abertura",
    
    newText("<p> Clique no botão para assistir ao vídeo em Libras</p>")
    ,
    newVideo("video", "Abertura.mov")
    .disable(0.01)
    .print()
    .center()
    ,
    newButton("Assistir")
  .print()
  .callback( getVideo("video").test.playing()
    .success( self.stop() )
    .failure( self.play() )
    ,
    newText("<p>Olá</p>")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p>Este experimento consiste em ler algumas sentenças e responder perguntas de compreensão sobre elas.</p>")
     .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p><strong>ATENÇÃO</strong>: Este experimento só funciona corretamente se realizado em um <strong>computador</strong>.</p>")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p>Antes de prosseguir, responda as perguntas a seguir:<p>")
     .css("font-size","1.2em")
    .print()
    .center()
    ,
     newButton("Próximo")
    .css("font-size","1.2em")
    .print()
    .center()
    .wait())
);

newTrial (Pergunta1,
    defaultText
    ,
    newText("<p> Clique no botão para assistir ao vídeo em Libras</p>")
    ,
    newVideo("video", "Pergunta_nome_e-mail_idade.mov")
    .disable(0.01)
    .print()
    .center()
    ,
    newButton("Assistir")
  .print()
  .center()
  .callback( getVideo("video").test.playing()
    .success( self.stop() )
    .failure( self.play() )
    ,
    newText("<p>Escreva seu NOME COMPLETO na caixa abaixo.</p>")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newTextInput("Nome")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p>Por favor, escreva seu E-MAIL na caixa abaixo.</p>")
     .css("font-size","1.2em")
    .print()
    .center()
    ,
    newTextInput("Email")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p>Escreva sua IDADE na caixa abaixo.</p>")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newTextInput("Idade")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newButton("Próximo")
    .css("font-size","1.2em")
    .print()
    .center()
    .wait()
    ,
    newVar("ID")
    .global()
    .set(getTextInput("Nome"))
    ,
    newVar("EMAIL")
    .global()
    .set(getTextInput("Email"))
    ,
    newVar("IDADE")
    .global()
    .set(getTextInput("Idade"))
) 
    .log("ID", getVar("ID"))
    .log("EMAIL", getVar("EMAIL"))
    .log("IDADE", getVar("IDADE"))
);

newTrial ("Pergunta2",
    defaultText
    ,  
    newVideo("video", "Pergunta_nivel de formacao.mov")
    .disable(0.01)
    .print()
    .center()
    ,
    newButton("Assistir")
  .print()
  .center
  .callback( getVideo("video").test.playing()
    .success( self.stop() )
    .failure( self.play() )
    ,
    newText("<p>Selecione sua ESCOLARIDADE na caixa abaixo<p>") 
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newDropDown("Escolaridade")
    .settings.add( "Ensino Superior Incompleto","Ensino Superior Completo", "Especialização", "Mestrado" , "Doutorado")
    .print()
    .center()
    ,
    newButton("Próximo")
    .css("font-size","1.2em")
    .print()
    .center()
    .wait()
    ,
    newVar("Escolaridade")
    .global()
    .set(getTextInput("Escolaridade"))
)
    .log("ESCOLARIDADE", getVar("Escolaridade"))
);
newTrial ("Pergunta3",
    defaultText
        ,  
        newVideo("video", "Pergunta_usa libras.mov")
    .disable(0.01)
    .print()
    .center()
    ,
    newButton("Assistir")
  .print()
  .center()
  .callback( getVideo("video").test.playing()
    .success( self.stop() )
    .failure( self.play() )
    ,
    newText("<p>Você usa Libras como principal forma de comunicação?<p>") 
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newDropDown("Comunicação")
    .settings.add( "Sim","Não")
    .print()
    .center()
     ,
    newButton("Próximo")
    .css("font-size","1.2em")
    .print()
    .center()
    .wait()
    ,
    newVar("Comunicação")
    .global()
    .set(getTextInput("Comunicação"))
)
    .log("Comunicação", getVar("Comunicação"))
);
newTrial ("Pergunta4",
    defaultText
    ,  
    newVideo("video", "Pergunta_nivel de leitura.mov")
    .disable(0.01)
    .print()
    .center()
    ,
    newButton("Assistir")
    .print()
    .center()
    .callback( getVideo("video").test.playing()
    .success( self.stop() )
    .failure( self.play() )
    ,
    newText("<p>Qual é seu grau de entendimento da Língua Portuguesa na leitura de informações do cotidiano, como em notícias ou em redes sociais?<p>") 
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newDropDown("Nível LP")
    .settings.add( "Texto acadêmico para estudo","Notícias de jornal ou revista","Redes sociais como WhatsApp, Instagran, Faceboock, outros","Livros","Receitas","Outros")
    .print()
    .center()
    ,
    newButton("Próximo")
    .css("font-size","1.2em")
    .print()
    .center()
    .wait()
    ,
    newVar("Nível LP")
    .global()
    .set(getTextInput("Nível LP"))
)
    .log("Nível LP", getVar("Nível LP"))
);
newTrial ("Pergunta5",
    defaultText
    ,  
    newVideo("video", "Pergunta_tempo de leitura.mov")
    .disable(0.01)
    .print()
    .center()
    ,
    newButton("Assistir")
    .print()
    .center()
    .callback( getVideo("video").test.playing()
    .success( self.stop() )
    .failure( self.play() )
    ,
    newText("<p>Quanto tempo você se dedica à leitura por semana?<p>") 
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newDropDown("Tempo de leitura")
    .settings.add( "30 minutos","2h","4h","5h","6h ou mais")
    .print()
    .center()
    ,
    newButton("Próximo")
    .css("font-size","1.2em")
    .print()
    .center()
    .wait()
    ,
    newVar("Tempo de leitura")
    .global()
    .set(getTextInput("Tempo de leitura"))
)
    .log("Tempo de leitura", getVar("Tempo de leitura"))
);
newTrial("Orientação",
    
    newText("<p> Clique no botão para assistir ao vídeo em Libras</p>")
    ,
    newVideo("video", "Orientacao.mov")
    .disable(0.01)
    .print()
    .center()
    ,
    newButton("Assistir")
  .print()
  .callback( getVideo("video").test.playing()
    .success( self.stop() )
    .failure( self.play() )
    ,
    newText("<p>Orientações</p>")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p>Neste teste você vai ler sentenças. Para isso precisa apertar a <strong>BARRA DE ESPAÇO</strong> do teclado para aparecer cada um dos pedaços da sentença. Você deve ler com atenção e na sua velocidade natural.</p>")
     .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p>Depois da leitura você vai ver uma pergunta sobre a sentença e responder <strong>SIM</strong> com a TECLA <strong>“S”</strong> ou <strong>NÃO</strong> com a TECLA <strong>“N”</strong>.</p>")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p>Esse teste demora mais ou menos 10 minutos. Por favor, Certifique-se de que você está em um lugar tranquilo e silencioso para que não haja interrupções. Se precisar parar no meio do teste por algum motivo, não aperte o botão <strong>PRÓXIMO</strong> até poder voltar.<p>")
     .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p>Vamos fazer um treino com 3 sentenças para depois começar o teste de verdade.<p>")
     .css("font-size","1.2em")
    .print()
    .center()
    ,
     newButton("Iniciar Treino")
    .css("font-size","1.2em")
    .print()
    .center()
    .wait())
);

newTrial("telatreino")
    ,
    Template("Sentenças Treino.csv",
    variable => newTrial( "Treino"
    ,
    newController("DashedSentence", {s: variable.Sentenca} )
    .css("font-size","1.4em")
    .print()
    .center()
    .log()
    .wait()
    .remove()
    ,
    newText("pergunta", variable.Pergunta)
    .css("font-size","1.4em")
    .center()
    ,
    newText("S",  "Sim (S)")
    .css("font-size","1.4em")
    ,
    newText("N", "Não (N)")
    .css("font-size","1.4em")
    ,
    newCanvas("Canvas_treino", 1200, 600)
    .add(100, 0, getText("pergunta"))
    .add(70, 150, getText("C"))
    .add(450, 150, getText("M"))
    .print()
    .center()
    ,
    newSelector()
    .add( getText("S") , getText("N") )
    .keys(        "S"    ,       "N"   )
    .log()
    .wait()
    ,
    getCanvas("Canvas_treino")
    .remove()
    ,
    newButton("Próximo")
    .print()
    .center()
    .css("font-size","1.2em")
    .wait()
)
    .log("Grupo", variable.Grupo)
    .log("Item", variable.Item)
);

newTrial("start"
    ,
    newText("<p> Clique no botão para assistir ao vídeo em Libras</p>")
    ,
    newVideo("video", "Iniciar teste.mov")
    .disable(0.01)
    .print()
    .center()
    ,
    newButton("Assistir")
  .print()
  .callback( getVideo("video").test.playing()
    .success( self.stop() )
    .failure( self.play() )
    ,
    newText("<p>Agora que você já praticou, podemos começar o experimento.</p>")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p>Aperte <strong>INICIAR</strong> quando estiver pronto(a) para começar.</p>")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newButton("INICIAR")
        .print()
        .center()
        .css("font-size","1.2em")
        .wait())
);

newTrial("sentenças")
    ,
    Template("Tabela_Itens_Parte 1_GS.csv",
    variable => newTrial( "sentenças"
    ,
    newController("DashedSentence", {s: variable.Sentenca} )
    .css("font-size","1.4em")
    .print()
    .center()
    .log()
    .wait()
    .remove()
    ,
    newText("pergunta", variable.Pergunta)
    .css("font-size","1.4em")
    .center()
    ,
    newText("S",  "Sim (S)")
    .css("font-size","1.4em")
    ,
    newText("N", "Não (N)")
    .css("font-size","1.4em")
    ,
    newCanvas("Canvas_sentenças", 1200, 600)
    .add(100, 0, getText("pergunta"))
    .add(70, 150, getText("C"))
    .add(450, 150, getText("M"))
    .print()
    .center()
    ,
    newSelector()
    .add( getText("S") , getText("N") )
    .keys(        "S"    ,       "N"   )
    .log()
    .wait()
    ,
    getCanvas("Canvas_treino")
    .remove()
    ,
    newButton("Próximo")
    .print()
    .center()
    .css("font-size","1.2em")
    .wait()
)
    .log("Grupo", variable.Grupo)
    .log("Item", variable.Item)
);
    PennController.SendResults;
 
 newTrial("final"
    ,
    newText("<p> Clique no botão para assistir ao vídeo em Libras</p>")
    ,
    newVideo("video", "Iniciar teste.mov")
    .disable(0.01)
    .print()
    .center()
    ,
    newButton("Assistir")
  .print()
  .callback( getVideo("video").test.playing()
    .success( self.stop() )
    .failure( self.play() )
    ,
    newText("<p>A primeira etapa do teste chegou ao fim!</p>")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p>Por favor, acesse o link que você receberá por e-mail para completar a segunda etapa do teste e concluir a sua participação.</p>")
    .css("font-size","1.2em")
    .print()
    .center()
    ,
    newText("<p>Muito Obrigada!</p>")
    .css("font-size","1.4em")
    .center()
    .print()
    .wait())
.setOption("countsForProgressBar", false)
);
PennController.SendResults;
PennController.ResetPrefix(null);
