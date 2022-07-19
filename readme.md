<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->
# Título do Trabalho

#### Aluno: [Camilo Lopes Costa](https://github.com/milocosta)
#### Orientador: [Felipe Borges](https://github.com/FelipeBorgesC)
<!--#### Co-orientador(/a/es/as): [Nome Sobrenome](https://github.com/link_do_github) e [Nome Sobrenome](https://github.com/link_do_github). <!-- caso não aplicável, remover esta linha -->

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->
- [Link para o código](https://github.com/milocosta/projetofinal/blob/develop/script/main.ipynb). <!-- caso não aplicável, remover esta linha -->

- [Link para a monografia](https://github.com/milocosta/projetofinal). <!-- caso não aplicável, remover esta linha -->

- Trabalhos relacionados: <!-- caso não aplicável, remover estas linhas -->
    - [BERTimbau](https://github.com/neuralmind-ai/portuguese-bert)
    - [Introduction to Information Retrieval](https://www.kaggle.com/code/vabatista/introduction-to-information-retrieval)
    - [Question Answering BERT Base Cased Squad - PT](https://colab.research.google.com/drive/18ueLdi_V321Gz37x4gHq8mb4XZSGWfZx?usp=sharing)
    - [Portuguese BERT base cased Q&A, finetuned on SQUAD v1.1](https://huggingface.co/pierreguillou/bert-base-cased-squad-v1.1-portuguese?context=Meu+nome+%C3%A9+John%2C+tenho+20+anos%2C+moro+no+Brasil.+Estudo+no+Canad%C3%A1.&question=Onde+eu+estudo%3F)
    - [Haystack by Deepset](https://haystack.deepset.ai/overview/intro)
    - [Better Retrieval via Dense Passage Retrieval (DPR)](https://colab.research.google.com/github/deepset-ai/haystack/blob/master/tutorials/Tutorial6_Better_Retrieval_via_DPR.ipynb)
    - [roberta-base for QA](https://huggingface.co/deepset/roberta-base-squad2)

---

### Resumo
<!-- trocar o texto abaixo pelo resumo do trabalho, em português -->
Este trabalho abordará a aplicação Document Retrieval através do Q&A. Através de um parâmetro de entrada dado pelo usuário, uma busca será feita no repositório contendo as obras de Machado de Assis, no formato .txt, e retornará como resposta os 3 primeiros que obtiverem melhor resultado (score).
As obras contidas neste repositório são:
* Ressurreição;
* A Mão e a Luva;
* Helena;
* Iaiá Garcia;
* Memórias Póstumas de Brás Cubas;
* Casa Velha;
* Quincas Borba;
* Dom Casmurro;
* Esaú e Jacó;
* Memorial de Aires;


### Abstract <!-- Opcional! Caso não aplicável, remover esta seção -->
<!-- trocar o texto abaixo pelo resumo do trabalho, em inglês -->
This work will approach the Document Retrieval application through Q&A. Through an input parameter given by the user, a search will be made in the repository containing the works of Machado de Assis, in .txt format, and the first 3 that obtain the best result (score) will return as an answer.
The works contained in this repository are:
* Resurrection;
* The Hand and the Glove;
* Helen;
* Iaiá Garcia;
* The Posthumous Memoirs of Bras Cubas;
* Old house;
* Quincas Borba;
* Dom Casmurro;
* Esau and Jacob;
* Aires Memorial



### 1. Introdução

O NLP (do inglês *Natural Language Processing*) vem ganhando grande notoriedade no mercado hoje em dias para realizações de análises quantitativas e qualitativas (eg.: verificando os tesmos mais recorrentes nas avaliações e se a avaliação foi positiva ou negativa através da "análise de sentimentos"). Por se tratar de uma ramo muito abrangente da área de *Machine Learning*, muitos têm ganhado bastante atenção nos dias de hoje.

Das diversas aplicações de NLP, algumas que se destacam atualmente são:
* Speech Transcription: geração de texto através da fala ou geração da fala através de um texto;
* Neural Machine Translation (NMT): Tradução entre idiomas;
* Chatbots: Grande tendência entre as empresas por se tratar de robôs de conversa muito utilizado no atendimento ao cliente. Este tipo de algoritmo pode ser utilizado para utilização de voz ou por texto;
* Questions & Answers (Q&A): São muito utilizados para buscar possíveis resposta tanto na internet quanto num repositório, seja ele de documentos ou tabelas.
* Text Summarization: Realizar o resumo de textos de através de mecanismos extrativos no qual são extraídos trechos do texto que possuem maiores aproximações conforme o algoritmo de comparação (cosseno, etc) ou abstrativos que implica em ler o texto e escrever um resumo, ou seja, texto novo;
* Image Captioning: Geração de uma legenda através do reconhecimento de uma imagem;
* Video Captioning: Geração de legendas automáticas de vídeos;
* Análise de Sentimentos: Verificar se o texto possui características positivas, negativas ou neutras. Ex.: Positiva: 'Estou feliz...', Negativa: 'Estou triste...';
* Document Retrieval: retorna os documentos baseados em algum parâmetro de busca, seja ele uma pergunta do usuário ou um trecho;
* Passage Retrieval: pode-se dizer que trata-se de uma melhoraria do Document Retrieval possibilitando o retorno não apenas o documento mas também o trecho, página, etc. que se encontra a resposta

O Document Retrieval pode ser utilizado para diversas finalidades, desde buscar um livro que contenha algumas características e assim poder categorizá-lo até a possibilidade de verificar um Curriculum e direcionar à área que tenha maior afinidade (aplicação de RH).

A utilização do Q&A com o Document Retrieval abranje ainda mais sua aplicabilidade, fazendo com que um usuário tenha uma interação maior e possua um retorno com os resultados (documentos) que possuam maior *score* agilizando o processo de seleção de livros ou documentos.

Para o repositório utilizado, foram elaboradas as seguintes perguntas simples:
1. Quem foi Capitu?
2. Quem foi Mascarenhas?
3. Quem é a filha de Dona Eusébia e do Vilaça?
4. Rubião e Cristiano viram sócios em que?
5. Por que Estevão desejava morrer?
6. Salvador era pai de quem?
7. Com quem Jorge se casa ao voltar do Paraguai?
8. Por quem Pedro e Paulo estavam apaixonados?
9. Quem escreve sobre Tristão e Fidélia?
10. Como Escobar morreu?

O maior score para cada pergunta deverá ser o seguinte:
1. Dom Casmurro
2. Casa Velha
3. Memórias Póstumas de Brás Cubas
4. Quincas Borba
5. A Mão e a Luva
6. Helena
7. Iaiá Garcia
8. Esaú e Jacó
9. Memorial de Aires
10. Dom Casmurro

### 2. Modelagem

Para modelagem do problemas foram utilizados os conceitos BERT (do inglês *Bidirectional Encoder Representations from Transformers*) no qual utiliza como predição os termos entre as frase. Neste projeto foram utilizados 3 modelos para verificação dos scores apresentados nos quais 2 deles são do idioma inglês com um possibilidade de pré-processamento no idioma portugUês. São eles:
- Modelo Q&A de Pierre Guillou para idioma português.
- Modelo DPR (do inglês *Deep Passage Retrieval*) do projeto Haystack da equipe Deepset.
- Modelo BM25 da biblioteca `rank_bm25`.

O modelo DPR será analisado para execução sem pré-processamento (idioma inglês) e através do pré-processamento para verificação do idioma em português. Desta forma será possível avaliar o desempenho dos resultados para uma modelagem própria para o português quanto o impacto de um idioma diferente do padrão nos outros dois modelos.

### 3. Resultados

Após executação dos scripts afim de verificar os retornos que possuem a maior similarida, ou seja, os livros que possuem o maior score para o termo pesquisado, obtemos o seguinte:

* QA - Pierre Guillou

| Pergunta | Documento | Score | Resultado |
|------------- | :-------------: | ------------- | ------------- |
|Quem é Capitu? | domCasmurro.txt | 0.840419 | ✅ |
|Quem é Capitu? | memoriasBras.txt | 0.744943 | ❌ |
|Quem é Capitu? | helena.txt | 0.733090 | ❌ |
|Quem foi Mascarenhas? | esau.txt | 0.956288 | ❌ |
|Quem foi Mascarenhas? | quincas.txt | 0.817726 | ❌ |
|Quem foi Mascarenhas? | memoriasBras.txt | 0.594775 | ❌ |
|Quem é a filha de Dona Eusébia e do Vilaça? | memoriasBras.txt | 0.995128 | ✅ |
|Quem é a filha de Dona Eusébia e do Vilaça? | domCasmurro.txt | 0.893009 | ❌ |
|Quem é a filha de Dona Eusébia e do Vilaça? | quincas.txt | 0.847360 | ❌ |
|Rubião e Cristiano viram sócios em que? | domCasmurro.txt | 0.949915 | ❌ |
|Rubião e Cristiano viram sócios em que? | quincas.txt | 0.918761 | ✅ |
|Rubião e Cristiano viram sócios em que? | memorial-de-aires.txt | 0.902077 | ❌ |
|Por que Estevão desejava morrer? | memoriasBras.txt | 0.779468 | ❌ |
|Por que Estevão desejava morrer? | quincas.txt | 0.612361 | ❌ |
|Por que Estevão desejava morrer? | helena.txt | 0.581752 | ❌ |
|Salvador era pai de quem? | esau.txt | 0.993063 | ❌ |
|Salvador era pai de quem? | maoLuva.txt | 0.982218 | ❌ |
|Salvador era pai de quem? | domCasmurro.txt | 0.976742 | ❌ |
|Com quem Jorge se casa ao voltar do Paraguai? | iaia.txt | 0.946806 | ✅ |
|Com quem Jorge se casa ao voltar do Paraguai? | memoriasBras.txt | 0.884119 | ❌ |
|Com quem Jorge se casa ao voltar do Paraguai? | casaVelha.txt | 0.509564 | ❌ |
|Por quem Pedro e Paulo estavam apaixonados? | maoLuva.txt | 0.974591 | ❌ |
|Por quem Pedro e Paulo estavam apaixonados? | esau.txt | 0.753157 | ✅ |
|Por quem Pedro e Paulo estavam apaixonados? | domCasmurro.txt | 0.666831 | ❌ |
|Quem escreve sobre Tristão e Fidélia? | helena.txt | 0.881686 | ❌ |
|Quem escreve sobre Tristão e Fidélia? | memorial-de-aires.txt | 0.876177 | ✅ |
|Quem escreve sobre Tristão e Fidélia? | maoLuva.txt | 0.829158 | ❌ |
|Como Escobar morreu? | domCasmurro.txt | 0.895922 | ✅ |
|Como Escobar morreu? | quincas.txt | 0.642612 | ❌ |
|Como Escobar morreu? | memoriasBras.txt | 0.602220 | ❌ |

Podemos observar que 7 de 10 livros corretos encontram-se dentro do top3 para cada pergunta.

* Modelo DPR - Haystack (EN)

| Pergunta | Documento | Score | Resultado |
|------------- | :-------------: | ------------- | ------------- |
|Quem é Capitu? | quincas.txt | 0.797495 | ❌ |
|Quem é Capitu? | domCasmurro.txt | 0.697046 | ✅ |
|Quem é Capitu? | iaia.txt | 0.690444 | ❌ |
|Quem foi Mascarenhas? | quincas.txt | 0.518228 | ❌ |
|Quem foi Mascarenhas? | memoriasBras.txt | 0.427477 | ❌ |
|Quem foi Mascarenhas? | quincas.txt | 0.425616 | ❌ |
|Quem é a filha de Dona Eusébia e do Vilaça? | quincas.txt | 0.915381 | ❌ |
|Quem é a filha de Dona Eusébia e do Vilaça? | memoriasBras.txt | 0.912015 | ✅ |
|Quem é a filha de Dona Eusébia e do Vilaça? | memoriasBras.txt | 0.867204 | ✅ |
|Rubião e Cristiano viram sócios em que? | helena.txt | 0.861414 | ❌ |
|Rubião e Cristiano viram sócios em que? | memorial-de-aires.txt | 0.851872 | ❌ |
|Rubião e Cristiano viram sócios em que? | quincas.txt | 0.809805 | ✅ |
|Por que Estevão desejava morrer? | quincas.txt | 0.437841 | ❌ |
|Por que Estevão desejava morrer? | maoLuva.txt | 0.286587 | ✅ |
|Por que Estevão desejava morrer? | memorial-de-aires.txt | 0.278605 | ❌ |
|Salvador era pai de quem? | helena.txt | 0.786620 | ✅ |
|Salvador era pai de quem? | iaia.txt | 0.784398 | ❌ |
|Salvador era pai de quem? | esau.txt | 0.701406 | ❌ |
|Com quem Jorge se casa ao voltar do Paraguai? | iaia.txt | 0.588117 | ✅ |
|Com quem Jorge se casa ao voltar do Paraguai? | helena.txt | 0.525868 | ❌ |
|Com quem Jorge se casa ao voltar do Paraguai? | quincas.txt | 0.452068 | ❌ |
|Por quem Pedro e Paulo estavam apaixonados? | quincas.txt | 0.437352 | ❌ |
|Por quem Pedro e Paulo estavam apaixonados? | esau.txt | 0.291497 | ✅ |
|Por quem Pedro e Paulo estavam apaixonados? | quincas.txt | 0.290117 | ❌ |
|Quem escreve sobre Tristão e Fidélia? | memorial-de-aires.txt | 0.634639 | ✅ |
|Quem escreve sobre Tristão e Fidélia? | memorial-de-aires.txt | 0.513964 | ✅ |
|Quem escreve sobre Tristão e Fidélia? | domCasmurro.txt | 0.487883 | ❌ |
|Como Escobar morreu? | memoriasBras.txt | 0.704576 | ❌ |
|Como Escobar morreu? | esau.txt | 0.533779 | ❌ |
|Como Escobar morreu? | quincas.txt | 0.522244 | ❌ |

Podemos observar que 8 de 10 livros corretos encontram-se dentro do top3 para cada pergunta. Em alguns casos houveram duplicatas de livros uma vez que o modelo utilizado realiza uma "divisão" em n-caracteres, ou seja, um livro foi dividido em partes por conta do limite e assim pôde ser exibido mais de uma vez no retorno da modelagem.

* Modelo DPR - Haystack (PT)

| Pergunta | Documento | Score | Resultado |
|------------- | :-------------: | ------------- | ------------- |
|Quem é Capitu? | quincas.txt | 0.797495 | ❌ |
|Quem é Capitu? | domCasmurro.txt | 0.697046 | ✅ |
|Quem é Capitu? | iaia.txt | 0.690444 | ❌ |
|Quem foi Mascarenhas? | quincas.txt | 0.518228 | ❌ |
|Quem foi Mascarenhas? | memoriasBras.txt | 0.427477 | ❌ |
|Quem foi Mascarenhas? | quincas.txt | 0.425616 | ❌ |
|Quem é a filha de Dona Eusébia e do Vilaça? | quincas.txt | 0.915381 | ❌ |
|Quem é a filha de Dona Eusébia e do Vilaça? | memoriasBras.txt | 0.912015 | ✅ |
|Quem é a filha de Dona Eusébia e do Vilaça? | memoriasBras.txt | 0.867204 | ✅ |
|Rubião e Cristiano viram sócios em que? | helena.txt | 0.861414 | ❌ |
|Rubião e Cristiano viram sócios em que? | memorial-de-aires.txt | 0.851872 | ❌ |
|Rubião e Cristiano viram sócios em que? | quincas.txt | 0.809805 | ✅ |
|Por que Estevão desejava morrer? | quincas.txt | 0.437841 | ❌ |
|Por que Estevão desejava morrer? | maoLuva.txt | 0.286587 | ✅ |
|Por que Estevão desejava morrer? | memorial-de-aires.txt | 0.278605 | ❌ |
|Salvador era pai de quem? | helena.txt | 0.786620 | ✅ |
|Salvador era pai de quem? | iaia.txt | 0.784398 | ❌ |
|Salvador era pai de quem? | esau.txt | 0.701406 | ❌ |
|Com quem Jorge se casa ao voltar do Paraguai? | iaia.txt | 0.588117 | ✅ |
|Com quem Jorge se casa ao voltar do Paraguai? | helena.txt | 0.525868 | ❌ |
|Com quem Jorge se casa ao voltar do Paraguai? | quincas.txt | 0.452068 | ❌ |
|Por quem Pedro e Paulo estavam apaixonados? | quincas.txt | 0.437352 | ❌ |
|Por quem Pedro e Paulo estavam apaixonados? | esau.txt | 0.291497 | ✅ |
|Por quem Pedro e Paulo estavam apaixonados? | quincas.txt | 0.290117 | ❌ |
|Quem escreve sobre Tristão e Fidélia? | memorial-de-aires.txt | 0.634639 | ✅ |
|Quem escreve sobre Tristão e Fidélia? | memorial-de-aires.txt | 0.513964 | ✅ |
|Quem escreve sobre Tristão e Fidélia? | domCasmurro.txt | 0.487883 | ❌ |
|Como Escobar morreu? | memoriasBras.txt | 0.704576 | ❌ |
|Como Escobar morreu? | esau.txt | 0.533779 | ❌ |
|Como Escobar morreu? | quincas.txt | 0.522244 | ❌ |

Podemos observar que 8 de 10 livros corretos encontram-se dentro do top3 para cada pergunta. Em alguns casos houveram duplicatas de livros conforme explicado no caso anterior.

* BM25Okapi

| Pergunta | Documento | Score | Resultado |
|------------- | :-------------: | ------------- | ------------- |
Quem é Capitu? | domCasmurro.txt | 4.451809 | ✅ |
Quem é Capitu? | quincas.txt | 1.572012 | ❌ |
Quem é Capitu? | ressurreicao.txt | 1.568776 | ❌ |
Quem foi Mascarenhas? | quincas.txt | 1.566703 | ❌ |
Quem foi Mascarenhas? | ressurreicao.txt | 1.566145 | ❌ |
Quem foi Mascarenhas? | maoLuva.txt | 1.550557 | ❌ |
Quem é a filha de Dona Eusébia e do Vilaça? | memoriasBras.txt | 9.539631 | ✅ |
Quem é a filha de Dona Eusébia e do Vilaça? | iaia.txt | 5.608041 | ❌ |
Quem é a filha de Dona Eusébia e do Vilaça? | ressurreicao.txt | 5.606311 | ❌ |
Rubião e Cristiano viram sócios em que? | quincas.txt | 13.328757 | ✅ |
Rubião e Cristiano viram sócios em que? | iaia.txt | 3.282499 | ❌ |
Rubião e Cristiano viram sócios em que? | helena.txt | 2.300342 | ❌ |
Por que Estevão desejava morrer? | maoLuva.txt | 6.725565 | ✅ |
Por que Estevão desejava morrer? | iaia.txt | 2.651488 | ❌ |
Por que Estevão desejava morrer? | domCasmurro.txt | 2.254303 | ❌ |
Salvador era pai de quem? | helena.txt | 6.463614 | ✅ |
Salvador era pai de quem? | iaia.txt | 2.892272 | ❌ |
Salvador era pai de quem? | domCasmurro.txt | 2.852768 | ❌ |
Com quem Jorge se casa ao voltar do Paraguai? | iaia.txt | 11.013979 | ✅ |
Com quem Jorge se casa ao voltar do Paraguai? | maoLuva.txt | 8.404937 | ❌ |
Com quem Jorge se casa ao voltar do Paraguai? | memorial-de-aires.txt | 5.468255 | ❌ |
Por quem Pedro e Paulo estavam apaixonados? | esau.txt | 3.993422 | ✅ |
Por quem Pedro e Paulo estavam apaixonados? | memoriasBras.txt | 3.708351 | ❌ |
Por quem Pedro e Paulo estavam apaixonados? | domCasmurro.txt | 3.636246 | ❌ |
Quem escreve sobre Tristão e Fidélia? | memorial-de-aires.txt | 10.737606 | ✅ |
Quem escreve sobre Tristão e Fidélia? | helena.txt | 2.865621 | ❌ |
Quem escreve sobre Tristão e Fidélia? | maoLuva.txt | 2.720083 | ❌ |
Como Escobar morreu? | domCasmurro.txt | 6.376088 | ✅ |
Como Escobar morreu? | maoLuva.txt | 1.969889 | ❌ |
Como Escobar morreu? | ressurreicao.txt | 0.765925 | ❌ |

Podemos observar que 9 de 10 livros corretos encontram-se dentro do top3 para cada pergunta.

* BM25L

| Pergunta | Documento | Score | Resultado |
|------------- | :-------------: | ------------- | ------------- |
|Quem é Capitu? | domCasmurro.txt | 83.250801 | ✅ |
|Quem é Capitu? | quincas.txt | 66.663409 | ❌ |
|Quem é Capitu? | esau.txt | 64.138808 | ❌ |
|Quem foi Mascarenhas? | esau.txt | 26.924270 | ❌ |
|Quem foi Mascarenhas? | quincas.txt | 25.262600 | ❌ |
|Quem foi Mascarenhas? | memorial-de-aires.txt | 24.110393 | ❌ |
|Quem é a filha de Dona Eusébia e do Vilaça? | esau.txt | 986.128793 | ❌ |
|Quem é a filha de Dona Eusébia e do Vilaça? | quincas.txt | 954.404642 | ❌ |
|Quem é a filha de Dona Eusébia e do Vilaça? | memoriasBras.txt | 895.948385 | ✅ |
|Rubião e Cristiano viram sócios em que? | quincas.txt | 2662.750190 | ✅ |
|Rubião e Cristiano viram sócios em que? | esau.txt | 313.699856 | ❌ |
|Rubião e Cristiano viram sócios em que? | domCasmurro.txt | 281.310701 | ❌ |
|Por que Estevão desejava morrer? | maoLuva.txt729.614339 | ✅ |
|Por que Estevão desejava morrer? | quincas.txt309.632344 | ❌ |
|Por que Estevão desejava morrer? | esau.txt300.154604 | ❌ |
|Salvador era pai de quem? | helena.txt | 342.860667 | ✅ |
|Salvador era pai de quem? | esau.txt | 340.105797 | ❌ |
|Salvador era pai de quem? | quincas.txt | 337.923971 | ❌ |
|Com quem Jorge se casa ao voltar do Paraguai? | iaia.txt | 1555.876833 | ✅ |
|Com quem Jorge se casa ao voltar do Paraguai? | maoLuva.txt | 316.350096 | ❌ |
|Com quem Jorge se casa ao voltar do Paraguai? | quincas.txt | 238.416343 | ❌ |
|Por quem Pedro e Paulo estavam apaixonados? | esau.txt | 764.651031 | ✅ |
|Por quem Pedro e Paulo estavam apaixonados? | domCasmurro.txt | 248.672819 | ❌ |
|Por quem Pedro e Paulo estavam apaixonados? | quincas.txt | 229.034089 | ❌ |
|Quem escreve sobre Tristão e Fidélia? | memorial-de-aires.txt | 939.252204 | ✅ |
|Quem escreve sobre Tristão e Fidélia? | esau.txt | 259.672552 | ❌ |
|Quem escreve sobre Tristão e Fidélia? | domCasmurro.txt | 238.347296 | ❌ |
|Como Escobar morreu? | domCasmurro.txt | 306.564487 | ✅ |
|Como Escobar morreu? | esau.txt | 2.823061 | ❌ |
|Como Escobar morreu? | quincas.txt | 2.697297 | ❌ |

Podemos observar que 9 de 10 livros corretos encontram-se dentro do top3 para cada pergunta.

* BM25+

| Pergunta | Documento | Score | Resultado |
|------------- | :-------------: | ------------- | ------------- |
|Quem é Capitu? | domCasmurro.txt | 6.812792 | ✅ |
|Quem é Capitu? | quincas.txt | 3.046554 | ❌ |
|Quem é Capitu? | ressurreicao.txt | 3.045611 | ❌ |
|Quem foi Mascarenhas? | quincas.txt | 0.647112 | ❌ |
|Quem foi Mascarenhas? | ressurreicao.txt | 0.646949 | ❌ |
|Quem foi Mascarenhas? | maoLuva.txt | 0.642408 | ❌ |
|Quem é a filha de Dona Eusébia e do Vilaça? | memoriasBras.txt | 11.696299 | ✅ |
|Quem é a filha de Dona Eusébia e do Vilaça? | helena.txt | 6.897741 | ❌ |
|Quem é a filha de Dona Eusébia e do Vilaça? | domCasmurro.txt | 6.712698 | ❌ |
|Rubião e Cristiano viram sócios em que? | quincas.txt | 25.763926 | ✅ |
|Rubião e Cristiano viram sócios em que? | iaia.txt | 12.681740 | ❌ |
|Rubião e Cristiano viram sócios em que? | helena.txt | 11.410104 | ❌ |
|Por que Estevão desejava morrer? | maoLuva.txt | 11.989600 | ✅ |
|Por que Estevão desejava morrer? | iaia.txt | 6.814021 | ❌ |
|Por que Estevão desejava morrer? | domCasmurro.txt | 6.124424 | ❌ |
|Salvador era pai de quem? | helena.txt | 9.721434 | ✅ |
|Salvador era pai de quem? | iaia.txt | 4.928090 | ❌ |
|Salvador era pai de quem? | domCasmurro.txt | 4.889697 | ❌ |
|Com quem Jorge se casa ao voltar do Paraguai? | iaia.txt | 13.943929 | ✅ |
|Com quem Jorge se casa ao voltar do Paraguai? | maoLuva.txt | 10.526583 | ❌ |
|Com quem Jorge se casa ao voltar do Paraguai? | memorial-de-aires.txt | 6.363105 | ❌ |
|Por quem Pedro e Paulo estavam apaixonados? | esau.txt | 7.515468 | ✅ |
|Por quem Pedro e Paulo estavam apaixonados? | domCasmurro.txt | 6.031557 | ❌ |
|Por quem Pedro e Paulo estavam apaixonados? | memoriasBras.txt | 4.858863 | ❌ |
|Quem escreve sobre Tristão e Fidélia? | memorial-de-aires.txt | 17.579051 | ✅ |
|Quem escreve sobre Tristão e Fidélia? | helena.txt | 7.363493 ||
|Quem escreve sobre Tristão e Fidélia? | maoLuva.txt | 7.083650 ||
|Como Escobar morreu? | domCasmurro.txt | 11.795725 | ✅ |
|Como Escobar morreu? | maoLuva.txt | 6.363999 | ❌ |
|Como Escobar morreu? | ressurreicao.txt | 4.421122 | ❌ |

Podemos observar que 9 de 10 livros corretos encontram-se dentro do top3 para cada pergunta.


### 4. Conclusões

Podemos observar nos resultados obtidos das tabelas que o mais eficiente deles são os 3 modelos do BM25 com uma acurácia de 90% uma vez que todos os resultados corretos foram os que obtiveram o maior score, com uma observação ao BM25L na 3a pergunta.
Já os modelos utilizados para DPR, que foi estruturado para o idioma inglês, independente do pré-processamento, obtiveram os mesmos resultados e, alguns deles não foram o top score para a pergunta.
O modelo de Pierre Guillou, apesar de obter 7 acertos, todos os livros corretos apresentaram o maior score para cada pergunta. Um possível solução seria a otimização do algoritmo utilizado em sua modelagem uma vez que foi de Q&A.

Uma melhoria para este projeto seria possibilitar a leitura de documentos em outras formatações (PDF, DOC, ODT, etc) contidos nos repositórios. Desta forma será possível possível obter uma solução mais ampla e flexível. Também é possível uma melhoria no desenvolvimento de um modelo pré-treinado em portugues para DPR português uma vez que, ao buscar algum no Huggingface para o idioma em questão, retornou com nenhum resultado.

---

Matrícula: 202.100.135

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
