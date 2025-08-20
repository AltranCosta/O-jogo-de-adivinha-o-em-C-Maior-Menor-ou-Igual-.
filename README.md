📝 Descrição do Código

Este programa em C implementa um simples jogo de adivinhação chamado "Maior, Menor ou Igual". O jogador escolhe um número entre 1 e 100 e seleciona uma opção de comparação:

1 → Apostar que seu número é maior que o número do computador

2 → Apostar que seu número é menor que o número do computador

3 → Apostar que seu número é igual ao número do computador

O programa então gera aleatoriamente um número entre 1 e 100 (representando a jogada do computador), compara os dois valores com base na escolha do jogador e exibe se ele venceu ou perdeu.

🔍 Funcionalidades incluídas:

Geração de número aleatório usando rand()

Validação das entradas do jogador (tanto a opção quanto o número)

Comparação entre o número do jogador e o número do computador

Mensagens personalizadas de vitória ou derrota

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
