# lista6_lab
## Questão 01
Escreva um programa em C que utilize uma Estrutura aluno para conter duas notas, lidas do usuário, e sua média.

```c
#include <stdio.h>
struct alunos {
float notas[2];
float media;
};

int main(void) {
  struct alunos a;
  
  for(int i = 0; i < 2; i++){
    printf("Digite a %dª nota: ", i + 1);
    scanf("%f", &a.notas[i]);
  }

  a.media = (a.notas[0] + a.notas[1])/2;

  printf("A 1ª nota é: %.2f \nA 2ª nota é %.2f \nA média é %.2f", a.notas[0], a.notas[1], a.media);
  
  return 0;
}
```

## Questão 02
Escreva um programa em C que utilize uma Estrutura estoque que contém uma string com o nomePeca, um número inteiro para identificar o número da peça, o preço em ponto flutuante e um elemento inteiro para identificar o número do pedido.

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define carac 20
struct estoque {
char nomePeca[carac];
int  nmrPeca;
float preco;
int nmrPedido;
};

int main(void) {
  struct estoque e;
  puts("Insira o nome da peça: ");
  fgets(e.nomePeca, carac, stdin);
  puts("Insira o número de indentificação da peça: ");
  scanf("%d", &e.nmrPeca);
  puts("Insira o valor do preço da peça: ");
  scanf("%f", &e.preco);
  puts("Insira o número de indentificação do pedido: ");
  scanf("%d", &e.nmrPedido);
  return 0;
}
```

## Questão 03
Escreva um programa em C que gere um vetor com números aleatórios e calcule sua média. Organize uma Estrutura com as seguintes informações: ponteiro para a matriz, quantidade de elementos e a média.

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define MX 100
#define INI 0

void preencherVetor(int *, int , int , int );
void imprimirVetor(int *, int );

struct vetmedia {
int *matriz;
int qtd;
int media;

};

int main(void) {
  int soma = 0;
  struct vetmedia v;
  puts("Insira a quantidade de elementros na matriz: ");
  scanf("%d", &v.qtd);

  v.matriz = (int *)malloc(v.qtd * sizeof(int));
  preencherVetor(v.matriz, v.qtd, INI, MX);
  imprimirVetor(v.matriz, v.qtd);

  for(int i = 0; i < v.qtd; i++){
    soma += *(v.matriz + i);
  }
  v.media = soma/v.qtd;
  
  printf("%d", v.media);
  return 0;
}

void preencherVetor(int *pd, int qtd, int inicial, int qtdFaixa){
    srand(time(NULL));
    for (int k=0; k<qtd; k++){
        *(pd+k) = inicial + rand() % qtdFaixa;
    }
}

void imprimirVetor(int *pd, int qtd){
    for (int k=0; k<qtd; k++){
        printf("[%p] %d\n",pd+k,*(pd+k));
    }
}
```

## Questão 04

Escreva um programa em C que modifique a Questão 1 para conter um array com 3 alunos. Escreva uma função para calcular a média dos alunos.

```c
#include <stdio.h>
int mediaAlunos (float , float , float );

struct alunos {
float notas[2];
float media;
};

int main(void) {
  struct alunos a1, a2, a3;
  float mediaTotal;

  puts("Digite as notas do primeiro aluno: ");
  for(int i = 0; i < 2; i++){
    printf("Digite a %dª nota: ", i + 1);
    scanf("%f", &a1.notas[i]);
  }
  
  puts("\nDigite as notas do segundo aluno: ");
  for(int i = 0; i < 2; i++){
    printf("Digite a %dª nota: ", i + 1);
    scanf("%f", &a2.notas[i]);
  }
  puts("\nDigite as notas do terceiro aluno: ");
  for(int i = 0; i < 2; i++){
    printf("Digite a %dª nota: ", i + 1);
    scanf("%f", &a3.notas[i]);
  }
  
  a1.media = (a1.notas[0] + a1.notas[1])/2;
  a2.media = (a2.notas[0] + a2.notas[1])/2;
  a3.media = (a3.notas[0] + a3.notas[1])/2;
  
  puts("\n--------- Primeiro Aluno ---------");
  printf("A 1ª nota é: %.2f \nA 2ª nota é %.2f \nA média é %.2f", a1.notas[0], a1.notas[1], a1.media);
  puts("\n----------------------------------\n");

  puts("--------- Segundo Aluno ---------");
  printf("A 1ª nota é: %.2f \nA 2ª nota é %.2f \nA média é %.2f", a2.notas[0], a2.notas[1], a2.media);
  puts("\n--------------------------------\n");
  
  puts("--------- Terceiro Aluno ---------");
  printf("A 1ª nota é: %.2f \nA 2ª nota é %.2f \nA média é %.2f",
a3.notas[0], a3.notas[1], a3.media);
  puts("\n---------------------------------\n");
  
  mediaTotal = mediaAlunos(a1.media, a2.media, a3.media);

  printf("A média dos alunos é %.2f", mediaTotal);
  return 0;
}

int mediaAlunos (float media1, float media2, float media3) {
  int media;
  media = (media1 + media2 + media3)/3;
  return media;
}
```

## Questão 05


Crie uma Estrutura 'disciplina' em que um dos campos corresponde também a uma estrutura 'professor'.

```c
#include <stdio.h>

 stuct professor {
  int nomeP;
};

struct disciplina {
int nomeD;
int qtdH;
struct professor prof;
};

int main(void) {
  printf("Hello World\n");
  return 0;
}
```
