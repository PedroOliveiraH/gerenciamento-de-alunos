#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <string.h>

#define tam 50

struct cadastroAluno{
    char nome[tam];
    float nota[3];
};

typedef struct cadastroAluno aluno;
                aluno lista[tam];

void incluir();
void localizar();
void listar();
void remover();
void editar();

int conteAluno = 0;
int i, j, a;

char busca[tam];

int main(){
    setlocale(LC_ALL,"portuguese");

    int c;

    do{
        system("cls");
        printf("\tInsira 0 para sair do programa.\n");
        printf("\tInsira 1 para incluir um aluno e suas notas.\n");
        printf("\tInsira 2 para localizar um aluno e exibir sua soma de notas\n");
        printf("\tInsira 3 para listar todos os alunos e suas notas,.\n");
        printf("\tInsira 4 remover um aluno e suas notas.\n");
        printf("\tInsira 5 para editar os dados de um aluno.\n");
        printf("\n\tInsira um valor de 0 a 5: ");
        scanf("%d", &c);

       switch(c){
            case 1:
                printf("\n\t########### INCLUIR ###########\n");
                incluir();
                break;
            case 2:
                printf("\n\t########### LOCALIZAR ###########\n");
                localizar();
                break;
            case 3:
                printf("\n\t########### LISTAR ###########\n");
                listar();
                break;
            case 4:
                printf("\n\t########### REMOVER ###########\n");
                remover();
                break;
            case 5:
                printf("\n\t########### EDITAR ###########\n");
                editar();
                break;
            default:
                printf("\n\tOpção inválida!\n");
                break;
        }
        printf("\n\tInsira 0 para confirmar a saida ou 1 para continuar: ");
        scanf("\t%d", &c);

        }while(c);

    system("pause");

}

void incluir(){
        printf("\tInsira o nome do aluno: ");
        fflush(stdin);
        scanf("%[^\n]s", &lista[conteAluno].nome);
        for(i=0;lista[conteAluno].nome[i] != '\0';i++){
            lista[conteAluno].nome[i] = toupper(lista[conteAluno].nome[i]);
            }
            for(i=0; i<3;i++){
                printf("\n\tInsira a %d° nota do aluno: ", i+1);
                fflush(stdin);
                scanf("%f", &lista[conteAluno].nota[i]);
            }
            conteAluno++;
}

void localizar(){
        float soma=0;

        for(i=0; i<conteAluno;i++){
            printf("\n\tAluno: %s", lista[i].nome);
            }
        printf("\t\n\tDigite o nome do aluno: ");
        fflush(stdin);
        scanf(" %[^\n]s", busca);
        for(i=0;busca[i] != '\0';i++){
            busca[i] = toupper(busca[i]);
            }
        for(i=0; i<conteAluno;i++){
            soma=0;
            if(strstr(lista[i].nome, busca)){
                for(j=0; j<3;j++){
                    soma+=lista[i].nota[j];
                    }
            printf("\n\tAluno: %s", lista[i].nome);
            printf("\n\tA soma das notas: %.2f\n", soma);
            }
        }
}

void listar(){
    for(i=0; i<conteAluno; i++){
        printf("\n\tAluno: %s.\n", lista[i].nome);
            for(j=0; j<3;j++){
                printf("\tNota %d: %.2f.\n",j+1, lista[i].nota[j]);
            }
    }
}

void remover(){
    for(i=0; i<conteAluno;i++){
        printf("\n\tAluno: %s", lista[i].nome);
        }
    printf("\t\n\tDigite o nome do aluno que deseja remover: ");
    fflush(stdin);
    scanf(" %[^\n]s", busca);
    for(i=0;busca[i] != '\0';i++){
        busca[i] = toupper(busca[i]);
    }
    printf("\t\n\tVocê tem certeza que deseja remover esse aluno ? ");
    printf("\t\n\tDigite 1 para confirmar a remoção ou digite 0 para cancelar.\n");
    fflush(stdin);
    scanf("%d", &a);
    if(a == 1){
        for(i=0; i<conteAluno;i++)
            if(strstr(lista[i].nome, busca)){
                do{
                    strcpy(lista[i].nome, lista[i+1].nome);
                    lista[i].nota[0] = lista[i+1].nota[0];
                    lista[i].nota[1] = lista[i+1].nota[1];
                    lista[i].nota[2] = lista[i+1].nota[2];
                    i++;
                }while(i<conteAluno-1);
            }
        conteAluno--;
    }
}

void editar(){
    for(i=0; i<conteAluno;i++){
        printf("\n\t%d - Aluno: %s", i, lista[i].nome);
        }
    printf("\t\n\tDigite o número do aluno que deseja editar os dados: ");
    fflush(stdin);
    scanf("%d", &i);
    printf("\n\t%d - Aluno: %s", i, lista[i].nome);
    for(j=0; j<3;j++)
        printf("\n\t%d° nota do aluno: %.2f", j+1, lista[i].nota[j]);
    printf("\t\n\tDigite 0 para cancelar a edição, digite o 1 para editar o nome ,digite 2 para editar as notas: ");
    scanf("%d", &a);
    if(a == 1){
        fflush(stdin);
        printf("\t\n\tEdite o nome: ");
        fflush(stdin);
        scanf("%[^\n]s", &lista[i].nome);
        for(j=0;lista[i].nome[j] != '\0';j++){
            lista[i].nome[j] = toupper(lista[i].nome[j]);
            }
        fflush(stdin);
    }else if(a == 2){
        fflush(stdin);
        printf("\t\n\tEdite as notas.");
        for(j=0; j<3;j++){
            printf("\n\t\tInsira a %d° nota do aluno: ", j+1);
            fflush(stdin);
            scanf("%f", &lista[i].nota[j]);
        }
    }
}
