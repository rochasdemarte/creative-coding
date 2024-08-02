# Aprendendo Processing

### Introdução

- Destinado a iniciantes interessados em aprender os fundamentos da programação.

- Processing é escolhido por sua simplicidade.

- O foco principal é ensinar como aprender a programar e criar arte interativa.

### Por que Aprender a Programar

- Programar permite desenvolver a criatividade e a autoexpressão através do potencial dos códigos.

- Todos podem aprender a programar.

- Os fundamentos da programação são essenciais e podem ser aplicados a outras linguagens e ambientes.

- Trabalhar com software em um computador muitas vezes começa entendendo as limitações do software e desejando superá-las.

### Visão Geral do Processing

- Processing é um caderno de esboços flexível e uma linguagem para aprender a programar no contexto das artes visuais.

- Simplifica muitos aspectos da programação, permitindo que iniciantes criem arte interativa rapidamente.

- A comunidade, Processing Foundation e o apoio.

### Começando com Processing

- Baixar Processing em [processing.org](https://processing.org/download) para seu sistema operacional.

- Instale e inicie o IDE do Processing.

- Visão geral da interface.

- Escrevendo e salvando código em arquivos PDE.

### Conceitos Básicos de Desenho

**Plano Cartesiano no Processing**

- Coordenadas de gráficos de computador: O canto superior esquerdo é (0, 0);

- X positivo é à direita

- Y positivo é para baixo.

**Comandos de exemplo:**

```Processing

size(width, height); // define o tamanho da tela.

frameRate(60); // configura a quantidade de frames por segundo.
noCursor(); // Para não renderizar o cursor do mouse na tela.

noStroke(); // Para não desenhar as linhas e contornos.
strokeWeight(10); // Para a largura das linhas e contornos.
point(x, y); // desenha um ponto.
line(x1, y1, x2, y2); // desenha uma linha entre dois pontos.

ellipseMode(CENTER); // Orienta como desenhar ellipses e círculos.
rectMode(CORNERS); // orienta como desenhar retângulos e quadrados.

```

**Formas**

```Processing

rect(x, y, width, height); // para retângulos.
square(x, y, squareSize) // para quadrados
quad(x1, y1, x2, y2, x3, y3, x4, y4) // para poligonos de lados diferentes
ellipse(x, y, width, height); // para elipses.
circle(x, y, circleSize); // para círculos.
triangle(x1, y1, x2, y2, x3, y3); // para triângulos

// Diversas formas podem ser desenhadas usando seus respectivos comandos.

```

**Cores**

```Processing

// para definir cores.
background();
stroke();
fill();

// RGB e escala de cinza: 
fill(r, g, b);
fill(g);

// Transparência com valores alfa.
fill(r, g, b, a);
fill(g, a);

```
**Texto**

```Processing
// para criar texto e posicioná-lo na tela.
textSize(tamanho);
textAlign(RIGHT);
text(texto, x, y);
```
Você ainda pode trocar de fonte, o arquivo da fonte desejada deve estar localizada em uma pasta de nome 'data' no mesmo local do sketch:
```Processing
PFont font;
// a fonte deve estar localizada na pasta "data".
font = loadFont("LetterGothicStd.otf");
textFont(font, 128);

```

```Processing
PFont mono;
// a fonte "andalemo.ttf" deve estar localizada na pasta "data".
mono = createFont("andalemo.ttf", 128);
background(0);
textFont(mono);
text("word", 48, 240);

```
Use ```textWidth``` para saber o tamanho horizontal do texto desejado em 
```Processing
textSize(112);
// 
char c = 'T';
float cw = textWidth(c);
text(c, 0, 160);
line(cw, 0, cw, 200); 

String s = "Tokyo";
float sw = textWidth(s);
text(s, 0, 340);
line(sw, 200, sw, 400);

```

### Trabalhando com Variáveis

**Tipos de Variáveis**

- Inteiro: ```int```

- Ponto flutuante: ```float```

- String: ```String```

- Boolean: ```boolean```

Elas armazenam valores de dados como coordenadas, tamanhos, cores, etc.

**Atribuição e Uso**

- Atribua valores usando ```=```.

- Exemplos de uso:
  - Movendo um círculo com ```x = x + 1;``` ou de uma forma resumida ```x += 1;``` para animar sua posição.
  - Determinando paramentros de funções ```rect(x, y, size, size);```

**Escopo de Variáveis**

- Variáveis Globais vs. Locais

**Variáveis Internas**

### Interatividade

- ```mouseX``` e ```mouseY``` para posição do mouse.

- ```pmouseX``` e ```pmouseY``` para posição do mouse um frame anterior.

- ```width``` e ```height``` para dimensões da tela.

- ```mousePressed``` para verificar o estado do botão do mouse.

- ```keyPressed``` para verificar o estado do teclado.

### Aleatoriedade

**Função Random**

- Use ```random(min, max)``` para gerar valores aleatórios.

- Valores aleatórios podem ser atribuídos a posições, tamanhos, cores, etc.


### Laços

**Estruturas de Controle**
- Declarações if, else para lógica de condições.

```Processing
if (x > y){
  // Aqui vai o código que será executado caso passe pela condição do 'if'
  x = x + 5;
}
```

- Laços for, while para iteração.

```Processing
// Em Java, existem duas principais formas de iterar com laços de repetição.

// Com while loops:

int i = 0;
while (i < 320) {
  line(120, i, 320, i);
  i = i + 20;
}

// E com for loops:

for (int i = 0; i < 320; i = i+20) {
  line(120, i, 320, i);
}

```
Podemos ter loops dentro de outros loops, chamados nested loops.
Eles são usados para iterar em mais de uma dimensão, por exemplo:

```Processing
// Para cada valor da variável 'i' passamos por todos os valores da variável 'j'.

for (int i = 120; i < 320; i = i+20) {
  for (int j = 0; j < 320; j = j+20) {
    point(i, j);
  }
}
```

**Combinando com Arrays**

Arrays são listas de dados, usamos para guardar elementos e valores de forma indexada em uma única variável. Os seus indexes começam a contar a partir de '0' seguindo a ordem numérica '0, 1, 2, 3,...' e assim por diante, de acordo com o tamanho da array.

- Criar e usar arrays para armazenar múltiplos pontos de dados.

```Processing
int[] numbers = new int[3];
numbers[0] = 90;  // atribui ao primeiro elemento
numbers[1] = 150; // atribui ao segundo elemento
numbers[2] = 30;  // atribui ao terceiro elemento

int a = numbers[0] + numbers[1]; // atribui à variável 'a' o valor de 240
int b = numbers[1] + numbers[2]; // atribui à variável 'b' o valor de 180 
```
Ou ainda de uma forma alternativa, você pode declarar os valores de cada elemento da sua lista

```Processing
int[] numbers = { 90, 150, 30 };  // syntaxe alternativa
int a = numbers[0] + numbers[1];  // atribui à variável 'a' o valor de 240
int b = numbers[1] + numbers[2];  // atribui à variável 'b' o valor de 180
```

- Iterar sobre arrays com laços.

```Processing
int degrees = 360;
float[] cos_vals = new float[degrees];
// Use um for() loop rapidamente iterar os valores de uma array.
for (int i=0; i < degrees; i++) {         
  cos_vals[i] = cos(TWO_PI/degrees * i);
}
```


### Funções

**Funções internas da línguagem**

Ao longo da aula, já conhecemos e usamos algumas funções próprias da línguagem:

```Processing
size();
print();
sin();
cos();
random();
rect();
line();
background();
map();
int();
```

**Definindo e Usando Funções**
- Crie blocos de código reutilizáveis.

- Sintaxe: 
```Processing
tipo nomeDaFunção(tipo parametro) {
  // escreva aqui seu código.
}
```

- Exemplo: 
```Processing
void drawCircle(float x, float y, int tamanho) {
  // código para desenhar um círculo
}
```

### Programação Orientada a Objetos (OOP)

**Classes e Objetos**
- Encapsulamento: Defina dados e métodos dentro de classes.

- Objetos são instâncias de classes.

- Exemplo: 
```Processing
class Ball {
  
  int x, y, w, h, Xvel, Yvel;
  
  Ball(int ballX, int ballY, int size, int speed){
    x = ballX;
    y = ballY;
    w = size;
    h = size;
    Yvel = speed;
    Xvel = int(speed * random(0, 1));
  }
  
  void display(){
    fill(239, 184, 212);
    ellipse(x, y, w, h);
  }
  
  void move(){
    x = x + Xvel;
    y = y + Yvel;
  }
  
  void collide(){
    if(x > width || x < 0){
      Xvel *= -1;
    }
    if(y > height || y < 0){
      Yvel *= -1;
    }
  }
}
```

**Construtor e Métodos**
- Uso de ```new``` para criar objetos.

```Processing
Ball ball = new Ball(x, y, tamanho, velocidade);
```
- Ainda podemos criar arrays de múltiplos objetos.

```Processing
Ball[] balls = new Ball[5];
for (int i = 0; i < balls.length; i++) {
  vectors[i] = new PVector();
}
```

### Projetos e Encerramento

**Mini-Projetos**
- Exemplo: Criar um elemento visual na tela, interagindo com variáveis em seus parâmetros, criando funções e usando as funções internas da linguagem, unindo todo o conhecimento da aula de hoje que puder colocar.

**Desafios e Aprendizado Adicional**
- Exercícios sugeridos para ampliar habilidades: Criar múltiplos elementos com o uso de classes e orientação de objetos.

- Agora, eu te incentivo a explorar tópicos mais avançados e recursos comunitários como fóruns e exemplos de sketchs da comunidade de artistas e desenvolvedores no [OpenProcessing](https://openprocessing.org/discover/).

### Conclusão

**Próximos Passos e Aprendizado Futuro**
- Na próxima aula veremos como manipular imagens e vídeos, através de seus pixels e outros parâmetros.

- Vamos explorar recursos sonoras, criando e manipulando ondas sonoras e suas propriedades.

- Vamos iniciar os conhecimentos em P5js, levando toda a capacidade do Processing para as redes online.

---
