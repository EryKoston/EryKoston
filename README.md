#include <stdio.h>
#include <stdlib.h>

typedef struct _snode {
    int valor;
    struct _snode *next;


}SNode;
typedef struct lista {
    SNode *begin;
}Lista;

SNode *Criar_No(int valor){

    SNode *No = (SNode*) calloc(1, sizeof(SNode));
    No -> valor = valor;
    No -> next = NULL;
    return No;
}

Lista *criarLista(){
    Lista *L = (Lista*)calloc(1, sizeof(Lista));
    L -> begin = NULL;
    return L;
};

void VerificarListaV(Lista *L){
    if(L->begin == NULL){
        printf("Lista vazia");
    }

}

void inserirInicio(Lista *L, int valor){

        SNode *p = Criar_No(valor);
        p ->next = L->begin;
        L -> begin = p;

}
void imprimirLista(const Lista *L){
    SNode *p = L->begin;

    while(p != NULL){
        printf("%d\n", p->valor);
        p = p->next;


    }



}

int main()
{
    Lista *L = criarLista();
    inserirInicio(L, 5);
    inserirInicio(L, 4);
    inserirInicio(L, 2);
    inserirInicio(L, 10);

    imprimirLista(L);


}
