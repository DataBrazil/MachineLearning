# Machine Learning - Projeto para Curso do TCU (09/2020) - por Fábio Gomes
Desafio do negócio - Anualmente são apresentadas na Câmara dos Deputados milhares de proposições legislativas. A adoção de classificação temática realizada de modo automático facilitaria atividades de monitoramento da tramitação de projetos de lei (PL) e outros tipos, como propostas de fiscalização e controle (PFC), segundo grupos temáticos de saúde, ampliando a transparência para a sociedade e agilizando atividades de elaboração legislativa e de fiscalização. Grupo de pesquisa da Câmara dos Deputados sobre Legislativo e Saúde, de que participo, desenvolveu tipologia hierarquizada para classificação de proposições legislativas relacionadas à saúde, contendo quatro grupos temáticos (também possui subcategorias) e pretende-se utilizar essa base para produzir modelo capaz de classificar novas proposições automaticamente.
Solução construída - Desenvolvo esse projeto de ML há mais de um ano (classificação supervisionada de textos de projetos de lei – PL - relacionados à saúde). Enfrentei muitos problemas na conversão de pdf em texto, pois a Câmara usou vários tipos de pdf ao longo do tempo. Em agosto de 2019, consegui elaborar alguns modelos por meio do R (base com 7575 PL), mas não consegui ir adiante com a avaliação e refinamento dos mesmos. O Random Forest foi o modelo mais promissor. Essa experiência anterior permitiu a detecção de erros de classificação no conjunto de treinamento e algumas intuições sobre o banco de dados e até sobre problemas na própria tipologia usada para a classificação. Esse curso permitiu o aprendizado do Python e a retomada do projeto. Verifiquei que meus dados são desbalanceados.Elaborei caderno no Google Colab com descrição da variável de texto e aplicação de modelo de NLP melhorou o desempenho que obtive há 1 ano com o R (Random Forest - RF). O modelo do SGD, com parâmetros selecionados por gridsearch, obteve acurácia similar (antes foi de 89,7% e agora de 90,89%), mas foram captados mais casos de saúde no conjunto de teste (antes foram 296 e agora 320). O f1 score do SDG foi de 0.9063. Foram realizados experimentos com SVM; XGBoost; Naive Bayes (NB); ensemble (NB, RF, SVM); construção de nova feature a partir da união de variáveis de texto; e adoção de limpeza do corpus, por meio do uso de stopwords em português (NLTK), comparando com o desempenho do TF-IDF sem limpeza prévia e também variando o número de palavras consideradas.Ainda foram realizados experimentos de classificação dos quatro grupos temáticos de saúde, por meio do RF, os quais obtiveram desempenho inferior ao da classificação da dimensão saúde. Foram geradas planilhas para verificação das discrepâncias entre a classificação e a predição, permitindo a identificação de erros do classificador humano e de situações em que o modelo RF apresentava maiores dificuldades de desempenho. Foram identificados as próximas etapas e necessidades para refinar os modelos.
Fonte de dados - O inteiro teor do texto das proposições legislativas pode ser extraído de arquivos pdf, disponibilizados na Internet no site de dados abertos da Câmara dos Deputados. Ref: https://dadosabertos.camara.leg.br/swagger/api.html#staticfile. A listagem das proposições e de seus códigos de classificação, identificados por humanos estão disponíveis em planilhas eletrônicas e serão divulgadas em breve neste site, após revisão.
