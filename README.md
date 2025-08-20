/*
 ============================================================================
 Nome do Programa : Jogo Maior, Menor ou Igual
 Descrição        : Este programa implementa um jogo simples onde o jogador 
                    escolhe um número entre 1 e 100 e tenta adivinhar se ele 
                    é maior, menor ou igual ao número sorteado pelo computador.

 Funcionamento    :
    1. O computador gera um número aleatório entre 1 e 100.
    2. O jogador escolhe uma das três opções:
        - 1: Apostar que seu número é MAIOR que o do computador
        - 2: Apostar que seu número é MENOR que o do computador
        - 3: Apostar que seu número é IGUAL ao do computador
    3. O programa compara os números e informa se o jogador ganhou ou perdeu.

 Recursos Usados  :
    - Biblioteca <stdlib.h> para geração de números aleatórios
    - Biblioteca <time.h> para inicialização da semente aleatória
    - Validações de entrada para garantir que o jogador digite números válidos

 Autor            : [Altran Costa]
 Data de Criação  : [20/08/2025]
 ============================================================================
*/
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(){

    int numeroJogador, numeroComputador;
    int tipocomparacao;
     
    //gera numero aleatorio
    srand(time(0));
    numeroComputador = rand() % 100 + 1;// Numero entre 1 e 100;

    printf("Inicio do Jogo\n");
    printf("Bem-vindo ao jogo Maior, Menor ou Igual\n");
    printf("Você deve escolher um Número e o tipo de comparação.\n");
    printf("1 - Maior\n");
    printf("2 - Menor\n");
    printf("3 - Igual\n");
    printf("Escolha uma das opções:\n");
    scanf("%d", &tipocomparacao);

    if (tipocomparacao < 1 || tipocomparacao > 3) {
        printf("Opção Inválida! Escolha 1, 2 ou 3.\n");
        return 1;
    }

    printf("Digite seu número (entre 1 e 100): ");
    scanf("%d", &numeroJogador);

    if (numeroJogador < 1 || numeroJogador > 100){// fazer a validação do numero
        printf("Numero Inválido Digite um numero entre 1 e 100\n");
     return 1;
    }
    
    switch (tipocomparacao)
    {
    case 1:
        printf("Você escolheu a Opção Maior:\n");
        printf("Número do Jogador é:%d O número do Computador é:%d\n",numeroJogador, numeroComputador);
        numeroJogador > numeroComputador ? printf("### Parabéns Você Ganhou ####\n") : printf("!!! Que pena Você Perdeu !!!\n");
        break;
    case 2:
        printf("Você escolheu a Opção Menor:\n");
        printf("Número do Jogador é:%d O número do Computador é:%d\n",numeroJogador, numeroComputador);
        numeroJogador < numeroComputador ? printf("### Parabéns Você Ganhou ####\n") : printf("!!! Que pena Você Perdeu !!!\n");
        break;
    case 3:
        printf("Você escolheu a Opção Igual:\n");
        printf("Número do Jogador é:%d O número do Computador é:%d\n",numeroJogador, numeroComputador);
        numeroJogador == numeroComputador ? printf("### Parabéns Você Ganhou ####\n") : printf("!!! Que pena Você Perdeu !!!\n");
        break;
    
    default:
     printf("Opção Inválida!\n");
        break;
    }

    return 0;
}
