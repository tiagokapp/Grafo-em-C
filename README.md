# Grafo-em-C
Algoritmo para a criação de Grafos na Linguagem de Montagem C

//constante
#define maximo 10

#include<stdio.h>
#include<stdlib.h>
//variaveis 

int tamanho=0;
int grafo[maximo];
int ma[maximo][maximo];
int op =1;

//prototipação

int grafo_tamanho();
void grafo_desenhar();
void grafo_desenhar_matriz();
void grafo_desenhar();
void grafo_inserir();
void grafo_remover();
void manu_mostrar();

//função principal
int main(){
	int i;
	while (tamanho<=0 || tamanho> maximo){
		
		tamanho = grafo_tamanho();
		if (tamanho <=0 || tamanho>maximo){
			system("cls");
			printf("escolha um valor entre 1 e %d \n", maximo);
			
		}else {
			
			for(int i=0; i<tamanho; i++){
				grafo[i] = i;
			}
		}
	}
	
	while (op!=0){
		system("cls");
		
		grafo_desenhar();
		grafo_desenhar_matriz();
		manu_mostrar();
		
		scanf("%d",& op);
		switch(op){
			case 1 : grafo_inserir();
			
			case 2 : grafo_remover();
				
				default : printf("informe uma opção válida");
			
			
			
		}
	}
	
	 system("pause");
	return 0;
	
}


// definir um número de vértices do grafo
int grafo_tamanho(){
	
	int tamanho;
	printf("escolha a quantidade de vértices do grafo	");
	scanf("%d", &tamanho);
	
	
	return tamanho;	
	
}


//inserir aresta 


void  grafo_inserir(){
	int num1, num2;
	printf("Escolha o vértice de origem entre 0 a %d", tamanho -1);
	scanf("%d",&num1);
	printf("Escolha o vértice de origem entre 0 a %d", tamanho -1);
 	scanf("%d", &num2);


if (num1 >tamanho-1 || num2>tamanho-1 || num1<0 || num2<0){
	
	printf("\n os valores precisam estar entre O 2 %d \n", tamanho);
	system("pause");
	
}else {
	
	ma[num1][num2] = 1;
	ma[num2][num1] = 1;
	

}

}
 // remover a aresta
 
 
 void grafo_desenhar(){
 	int i;
 	printf("Lista de vértices \n ]");
 	for(int i=0; i<tamanho;i++){
 		printf("%d", grafo[i]);
	 }
	 
	 printf("] \n\n"); 	 
 	
 	
 }
 
 
 void grafo_desenhar_matriz(){
 	
 	int i, j;
 	printf("Matriz de adjacencia \n []");
 	for (int i=0; i<tamanho;i++){
 		for(int j=0;j<tamanho;j++){
 			
 			
 			printf("%d", ma[i][j]);
		 }
		 printf("\n");
	 }
 }
 
 
 // mostrar o menu de opções
 void menu_mostrar(){
 	
 	printf("\n escolha uma opção \n");
 	printf("1- inserir aresta \n ");
 	printf("2- Remover aresta \n");
 	printf("3-  sair ");
 	
 	
 	
 	
 }
