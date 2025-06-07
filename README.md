# Xadrezc

#include <stdio.h>

// ----------------------------
// Função recursiva para a TORRE (movendo para a direita)
// ----------------------------
void moverTorre(int passos) {
    if (passos == 0) return;  // Caso base
    printf("Direita\n");
    moverTorre(passos - 1);   // Chamada recursiva
}

// ----------------------------
// Função recursiva para a RAINHA (movendo para a esquerda)
// ----------------------------
void moverRainha(int passos) {
    if (passos == 0) return;
    printf("Esquerda\n");
    moverRainha(passos - 1);
}

// ----------------------------
// Função recursiva para o BISPO com loops aninhados para "Cima Direita"
// ----------------------------
void moverBispo(int passos) {
    if (passos == 0) return;

    // Loop externo (vertical)
    for (int v = 0; v < 1; v++) {
        // Loop interno (horizontal)
        for (int h = 0; h < 1; h++) {
            printf("Cima Direita\n");
        }
    }

    moverBispo(passos - 1);  // Recursão após uma casa percorrida
}

// ----------------------------
// Movimento do CAVALO com loops aninhados e controle de fluxo
// Agora movendo duas casas para cima e uma para a direita
// ----------------------------
void moverCavalo() {
    int movimentosVerticais = 2;
    int movimentosHorizontais = 1;
    int i, j;

    printf("\nMovimento do Cavalo:\n");

    for (i = 0; i < 3; i++) {  // Loop "maior" para simular tentativas ou múltiplos movimentos
        for (j = 0; j < movimentosVerticais + movimentosHorizontais; j++) {
            if (j < movimentosVerticais) {
                printf("Cima\n");
                continue;  // continua no loop interno para o próximo movimento
            }

            if (j == movimentosVerticais) {
                printf("Direita\n");
                break;  // Sai do loop após o "L"
            }
        }
        break;  // Apenas uma execução do movimento completo em "L"
    }
}

int main() {
    // Número de casas para cada peça
    int casasTorre = 5;
    int casasBispo = 5;
    int casasRainha = 8;

    // ----------------------------
    // MOVIMENTO DA TORRE
    // ----------------------------
    printf("Movimento da Torre:\n");
    moverTorre(casasTorre);

    // ----------------------------
    // MOVIMENTO DO BISPO
    // ----------------------------
    printf("\nMovimento do Bispo:\n");
    moverBispo(casasBispo);

    // ----------------------------
    // MOVIMENTO DA RAINHA
    // ----------------------------
    printf("\nMovimento da Rainha:\n");
    moverRainha(casasRainha);

    // ----------------------------
    // MOVIMENTO DO CAVALO
    // ----------------------------
    moverCavalo();

    return 0;
}
