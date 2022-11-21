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
