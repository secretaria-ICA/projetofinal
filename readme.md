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
2. Quem é Mascarenhas?
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
- Modelo BM25 do projeto Haystack da equipe Deepset.

Estes dois últimos serão analisados os valores tanto para a modelagem padrão (inglês) quanto para o idioma português (pré-processamento). Desta forma será possível avaliar o desempenho dos resultados para uma modelagem própria para o português quanto o impacto de um idioma diferente do padrão nos outros dois modelos.

### 3. Resultados

Analisando as tabelas, podemos verificar que...


### 4. Conclusões

Podemos verificar nas tabelas de resultados que...

Uma melhoria para esta solução é possibilitar a leitura de documentos, dos repositórios, que estejam em outro formato (PDF, DOC, ODT, etc) Desta forma será possível possível obter uma solução mais ampla e flexível.

---

Matrícula: 202.100.135

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
