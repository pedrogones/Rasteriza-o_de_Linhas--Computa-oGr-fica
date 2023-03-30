# Rasteriza-o_de_Linhas--Computa-oGr-fica
Introdução à Computação Gráfica

Discentes: Kalil de Souza Figueiredo Gomes Teotonio, João Victor Monteiro de Oliveira, Pedro Targino Gomes.
Data de Finalização: 28/03/2023 

Rasterização de Linhas 

1ª Função - PutPixel 

Permite que você defina o valor de um único pixel em uma janela gráfica. Essa função é geralmente usada em conjunto com outras funções gráficas para desenhar imagens, gráficos e animações em uma tela. Os parâmetros desta função são: X: a coordenada x do pixel que você deseja definir. Essa coordenada é medida em pixels a partir da borda esquerda da janela gráfica. Y: a coordenada y do pixel que você deseja definir. Essa coordenada é medida em pixels a partir da borda superior da janela gráfica. Para o pixel aparecer na posição (x, y) escolhida é necessário fazer o cálculo: i = x * 4 + y * 512 * 4, quando encontrado o valor de i, é necessário mudar o valor de FBptr (FBptr é um ponteiro para um buffer de quadros, um tipo de memória que é usado em programação gráfica para armazenar imagens em um formato que pode ser exibido em uma tela ou monitor. O FBptr é um tipo de ponteiro em C++ que aponta para o início do buffer de quadros).

 2ª Função - DrawLine 

Para esta, utilizamos o algoritmo de Bresenham, que tem como objetivo determinar quais pixels em uma grade retangular devem ser ligados para formar uma linha, objetivando suavizar a mesma. O algoritmo utiliza cálculos baseados em inteiros para determinar quais pixels devem ser iluminados. A maior dificuldade desse trabalho foi encontrar uma maneira de plotar linhas em todos os octantes da janela OpenGl, para isto, foi necessário observar que o algoritmo funciona corretamente, da forma padrão, para o primeiro octante e com uma inversão das variáveis dx e dy obtemos a segunda octante. Baseado nisso, apenas com algumas inversões de sinais e ordem de variáveis, para fazer o espelhamento, conseguimos desenhar em todas as octantes
 
3ª Função - DrawTriangle 

Foi implementada usando a função DrawLine(), feita anteriormente para plotar linhas retas na janela gráfica. A função DrawTriangle() recebe as coordenadas dos três pontos que formam o triângulo como argumentos (x1, y1), (x2, y2) e (x3, y3). Em seguida, a função DrawLine() é usada três vezes para desenhar os três lados do triângulo, conectando os pontos passados como argumentos. Enfim, a função DrawTriangle() basicamente apenas realiza a implementação da função DrawLine() 3 vezes. Na primeira chamada da função ela é chamada por dois pontos (x(Xi, Xf), y(Yi, Yf)), na segunda ela é implementada usando o mesmo Xf e Yf (posição final da última linha) e dois novos pontos que são as extremidades da segunda linha, e a terceira chamada da função ela recebe o parâmetro, respectivamente, Xi e Yi(da primeira linha) e Xf e Yf(da segunda linha), assim ligam-se as extremidades, finalizando o triângulo.  
