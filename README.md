# 2048
Implementação do jogo 2048 em C.

Trabalho final de Algoritmos e Programação (INF01202)
2048
Turmas A e B
Gabriel Simonetti Souza (turma A)
Vinícius Roratto Carvalho (turma B)
Introdução
O trabalho final da disciplina consiste em aplicar os conhecimentos de programação
estruturada em C, aprendidos durante o semestre, para implementar um jogo de puzzle
matemático conhecido como 2048 . Para tal, a dupla usou conhecimentos de vetores, funções,
ponteiros, iterações, condicionais e manipulação de arquivos para construir o programa.
Como utilizar:
A utilização do 2048 é bastante simples. Ao executar o arquivo 2048.exe, o usuário encontra um
menu com cinco opções, a maioria delas bem auto-explicativas:
- A primeira opção inicia um novo jogo, com a matriz e a pontuação zerada.
- A segunda lista os arquivos .txt e pede o nome de um jogo carregado na memória.
- A terceira lista as 10 melhores pontuações.
- A quarta mostra algumas configurações do jogo como tamanho do tabuleiro, cor e até idioma
do jogo.
- A quinta opção encerra o programa.
Ao iniciar o jogo:
As setas do teclado movem as peças do tabuleiro para direita, esquerda, para cima e para
baixo, a opção ESC sai do jogo, R zera a matriz e a pontuação e L lista arquivos salvos para
carregar um jogo salvo anteriormente. ESC pergunta se o usuário pretende salvar o jogo e volta
para o menu inicial.
Como o jogo foi idealizado:
O jogo todo é um grande switch/do while que dispara comandos executados pelo usuário
através do teclado em conjunto com a função getch, da biblioteca CONIO. Uma vez ativado o
comando, diversas funções são executadas e o programa volta ao início do loop até que o
usuário decida dar o comando de sair. A descrição serve tanto para o menu inicial de opçõescomo para a mecânica do 2048, que se repete até que o usuário ganhe o jogo, atingindo 2048,
perca a partida, ficando sem movimento, ou decida sair por conta própria utilizando um
comando de saída.
Diferente do pedido no edital, as funções estão divididas em quatro bibliotecas. A dupla
escolheu esta opção para uma melhor visualização de como o jogo está estruturado. A
biblioteca controles_2048, por exemplo, apresenta as funções necessárias para alterar o estado
do tabuleiro durante o jogo.
Entre as funções da tabela de controles é bom chamar atenção para que movem as “peças”
para direita, para esquerda e para cima dentro do tabuleiro. É importante entender como
funcionam estas operações, pois são os elementos mais importantes do funcionamento do
jogo.
Para explicar, vamos tomar como exemplo a função ““int controle_esquerda (int **M, int ordem,
int *score, int *soma)”. ela recebe a matriz do jogo, o tamanho da matriz, o score atual do jogo e
o valor da última soma.
O movimento funciona da seguinte maneira:
Uma iteração desloca, um de cada vez, elementos diferentes de zero da direita para a esquerda
nas linhas. O elemento mais a esquerda não se move, e os outros são copiados na próxima
coluna da esquerda até que encontrem um número diferente de zero, ou o final da tabela, então
a iteração pára. Após cada deslocamento para esquerda, o espaço ocupado no passado
recebe zero para liberar o movimento dos outros valores. Se dois elementos de mesmo valor
se encontrarem, acontece uma soma entre eles e o score é aumentado. A variável movimento
está ali para garantir que não será incluído 2 ou 4 aleatório no tabuleiro se o jogador mantiver
pressionando a tecla para o mesmo lado, mesmo com o movimento já efetuado para aquela
direção.
Na biblioteca Mecânica está outra das funções mais importantes do jogo: a função game, como
explicado anteriormente, é um grande switch que espera pelos comandos dos jogadores e
executa quando recebe uma tecla. Outras funções nesta biblioteca avisam se o jogo terminou,
manipulam arquivos de texto.
Na biblioteca Estrutura estão as funções responsáveis por “imprimir” números, scores e
tabuleiros no jogo e, por último, a biblioteca menu organiza elementos do menu inicial e de
opções.
