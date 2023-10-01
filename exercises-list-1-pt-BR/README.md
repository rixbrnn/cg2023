1. O que é a GLSL? Quais os dois tipos de shaders são obrigatórios no pipeline programável
da versão atual que trabalhamos em aula e o que eles processam?
   Resposta: GLSL significa OpenGL Shading Language, que é uma linguagem de programação de alto nível usada para programar shaders na API de gráficos OpenGL
   Os dois tipos de shaders que são geralmente considerados obrigatórios no pipeline gráfico programável moderno são:

Vertex Shader: Ele processa cada vértice e é responsável por transformar as coordenadas do vértice do espaço do objeto para o espaço de projeção. Pode também modificar cores, coordenadas de textura e outros atributos de vértice. Em resumo, um vertex shader determina a posição e outros atributos de dados de cada vértice.

Fragment Shader (às vezes chamado de Pixel Shader): Ele é executado para cada fragmento gerado pelo rasterizador e determina a cor final de cada pixel na tela. O fragment shader processa dados interpolados gerados pelo vertex shader e é responsável por aplicar efeitos como sombreamento, mapeamento de textura e outros efeitos pixel por pixel.
2. O que são primitivas gráficas? Como fazemos o armazenamento dos vértices na OpenGL?
Primitivas gráficas são basicamente os blocos de construção para criar imagens em computação gráfica, como pontos, linhas e triângulos, que são muito usados em OpenGL. Na OpenGL, para guardar os pontos (vértices) dessas primitivas, a gente usa algo chamado de Vertex Buffer Object (VBO), que é um jeito de passar os dados dos pontos para a OpenGL. Depois, a gente usa comandos específicos para dizer à OpenGL como usar esses pontos para desenhar as formas que queremos na tela.
3. Explique o que é VBO, VAO e EBO, e como se relacionam (se achar mais fácil, pode fazer
um gráfico representando a relação entre eles).
VBO, ou Vertex Buffer Object, é basicamente onde a gente guarda os dados dos pontos (vértices) das formas que queremos desenhar. Então, se a gente quer desenhar um triângulo, a gente põe as coordenadas dos três cantos do triângulo no VBO.

VAO, ou Vertex Array Object, é como uma configuração que diz para a OpenGL como ela deve entender os dados que estão no VBO. Ele guarda informações como quantos dados existem para cada ponto, que tipo de dado é (por exemplo, se é um número inteiro ou um decimal) e a que parte do gráfico se refere (como a posição ou a cor).

EBO, ou Element Buffer Object, é outro lugar onde podemos guardar dados, mas ele é mais usado para dizer à OpenGL quais pontos do VBO ela deve conectar para formar as primitivas gráficas. Por exemplo, se temos quatro pontos no VBO, podemos usar o EBO para dizer à OpenGL para conectar os pontos de forma a criar dois triângulos.

Na prática, quando vamos desenhar algo com OpenGL, a gente primeiro cria um VBO para guardar os dados dos pontos, depois cria um VAO para guardar as configurações de como interpretar esses dados, e, se necessário, um EBO para especificar como conectar os pontos. Quando tudo está configurado, a gente manda a OpenGL desenhar as formas usando essas configurações.
4. Analise o código fonte do projeto Hello Triangle. Localize e relacione os conceitos de
shaders, VBOs e VAO apresentados até então. Não precisa entregar nada neste exercício.
5. Faça o desenho de 2 triângulos na tela. Desenhe eles:
a. Apenas com o polígono preenchido: Resposta no commit `ee593dd`
b. Apenas com contorno: Resposta no commit `a7ae874`
c. Apenas como pontos: Resposta no commit `95ebb3a`
d. Com as 3 formas de desenho juntas: Resposta no commit `af3d527`
6. Faça o desenho de um círculo na tela, utilizando a equação paramétrica do círculo para
gerar os vértices. Resposta no commit `a6426d5`
 Depois disso:
a) Desenhe um octágono
b) Desenhe um pentágono
c) Desenhe um pac-man!
d) Desenhe uma fatia de pizza
e) DESAFIO: desenhe uma “estrela”
7. Desenhe uma espiral, assim:
UNIVERSIDADE DO VALE DO RIO DOS SINOS
8. Considerando o seguinte triângulo abaixo, formado pelos vértices P1, P2 e P3,
respectivamente com as cores vermelho, verde e azul.
a. Descreva uma possível configuração dos buffers (VBO, VAO e EBO) para
representá-lo.
b. Como estes atributos seriam identificados no vertex shader?
Agora implemente!
9. Faça um desenho em um papel quadriculado (pode ser no computador mesmo) e
reproduza-o utilizando primitivas em OpenGL. Neste exercício você poderá criar mais de um
VAO e fazer mais de uma chamada de desenho para poder utilizar primitivas diferentes, se
necessário.
10. Implemente (pode pegar do tutorial) uma classe para tratar os shaders a partir de
arquivos. FEITO EM AULA E ATUALIZADO O REPOSITÓRIO!
Entrega individual via Moodle (consulte a data de entrega no sistema)