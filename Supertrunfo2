#include <stdio.h>
#include <string.h>

// Estrutura para representar uma carta de cidade
typedef struct {
    char estado[50];
    int codigo;
    char nome[50];
    int populacao;
    float area;
    float pib;
    int pontosTuristicos;
} CartaCidade;

// Função para cadastrar os dados de uma carta
void cadastrarCarta(CartaCidade *carta) {
    printf("Digite o estado da cidade: ");
    scanf(" %[^\n]s", carta->estado); // Lê strings com espaços

    printf("Digite o código da cidade: ");
    scanf("%d", &carta->codigo);

    printf("Digite o nome da cidade: ");
    scanf(" %[^\n]s", carta->nome);

    printf("Digite a população da cidade: ");
    scanf("%d", &carta->populacao);

    printf("Digite a área da cidade (km²): ");
    scanf("%f", &carta->area);

    printf("Digite o PIB da cidade: ");
    scanf("%f", &carta->pib);

    printf("Digite o número de pontos turísticos: ");
    scanf("%d", &carta->pontosTuristicos);
}

// Função para exibir os dados de uma carta
void exibirCarta(CartaCidade carta) {
    printf("\n--- Dados da Cidade ---\n");
    printf("Estado: %s\n", carta.estado);
    printf("Código: %d\n", carta.codigo);
    printf("Nome: %s\n", carta.nome);
    printf("População: %d\n", carta.populacao);
    printf("Área: %.2f km²\n", carta.area);
    printf("PIB: %.2f\n", carta.pib);
    printf("Pontos Turísticos: %d\n", carta.pontosTuristicos);
}

// Função para comparar duas cartas com base em um atributo
void compararCartas(CartaCidade carta1, CartaCidade carta2, int atributo) {
    printf("\n--- Comparando Cartas ---\n");
    exibirCarta(carta1);
    exibirCarta(carta2);

    int resultado = 0; // 0: empate, 1: carta1 vence, 2: carta2 vence
    char atributoNome[50];

    switch (atributo) {
        case 1: // População
            strcpy(atributoNome, "População");
            printf("\nComparando por População...\n");
            if (carta1.populacao > carta2.populacao) {
                resultado = 1;
            } else if (carta2.populacao > carta1.populacao) {
                resultado = 2;
            }
            break;
        case 2: // Área
            strcpy(atributoNome, "Área");
            printf("\nComparando por Área...\n");
            if (carta1.area > carta2.area) {
                resultado = 1;
            } else if (carta2.area > carta1.area) {
                resultado = 2;
            }
            break;
        case 3: // PIB
            strcpy(atributoNome, "PIB");
            printf("\nComparando por PIB...\n");
            if (carta1.pib > carta2.pib) {
                resultado = 1;
            } else if (carta2.pib > carta1.pib) {
                resultado = 2;
            }
            break;
        case 4: // Pontos Turísticos
            strcpy(atributoNome, "Pontos Turísticos");
            printf("\nComparando por Pontos Turísticos...\n");
            if (carta1.pontosTuristicos > carta2.pontosTuristicos) {
                resultado = 1;
            } else if (carta2.pontosTuristicos > carta1.pontosTuristicos) {
                resultado = 2;
            }
            break;
        case 5: // Densidade Populacional
            strcpy(atributoNome, "Densidade Populacional");
            printf("\nComparando por Densidade Populacional...\n");
            float densidade1 = (float)carta1.populacao / carta1.area;
            float densidade2 = (float)carta2.populacao / carta2.area;

            if (densidade1 < densidade2) {
                resultado = 1; // carta1 vence (menor densidade)
            } else if (densidade2 < densidade1) {
                resultado = 2; // carta2 vence (menor densidade)
            }
            break;
        case 6: // Comparação Aninhada (Exemplo)
            strcpy(atributoNome, "Comparação Aninhada");
            printf("\nComparando por Comparação Aninhada (Exemplo)...\n");
            // Exemplo: Primeiro compara PIB, se empate, compara população
            if (carta1.pib > carta2.pib) {
                resultado = 1;
            } else if (carta2.pib > carta1.pib) {
                resultado = 2;
            } else {
                // PIB empatado, compara população
                if (carta1.populacao > carta2.populacao) {
                    resultado = 1;
                } else if (carta2.populacao > carta1.populacao) {
                    resultado = 2;
                }
            }
            break;
        default:
            printf("Atributo inválido para comparação.\n");
            return;
    }

    // Exibe o resultado da comparação
    if (resultado == 1) {
        printf("\nA carta vencedora é: %s (por %s)\n", carta1.nome, atributoNome);
    } else if (resultado == 2) {
        printf("\nA carta vencedora é: %s (por %s)\n", carta2.nome, atributoNome);
    } else {
        printf("\nEmpate!\n");
    }
}

// Função para exibir o menu e obter a escolha do usuário
int exibirMenu() {
    int escolha;
    printf("\n--- Menu de Comparação ---\n");
    printf("1. População\n");
    printf("2. Área\n");
    printf("3. PIB\n");
    printf("4. Pontos Turísticos\n");
    printf("5. Densidade Populacional\n");
    printf("6. Comparação Aninhada (Exemplo)\n");
    printf("Escolha o atributo para comparar: ");
    scanf("%d", &escolha);
    return escolha;
}

int main() {
    CartaCidade carta1, carta2;
    int atributo;

    printf("--- Cadastro da Carta 1 ---\n");
    cadastrarCarta(&carta1);

    printf("\n--- Cadastro da Carta 2 ---\n");
    cadastrarCarta(&carta2);

    atributo = exibirMenu();
    compararCartas(carta1, carta2, atributo);

    return 0;
}
