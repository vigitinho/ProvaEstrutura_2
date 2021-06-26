![](https://aluno.unipar.br/assets/img/unipar.png)
##### Universidade Paranaense - Curso TADS
Ano: 2° Série

Profºª: Geferson Luis Simonette
Matéria: Estrutura e classificação de dados

Aluno: Victor christoffoli
RA: 00211236 
---
# Estrutura de Dado
---
## _Árvore binária_
As árvores são estruturas de dados baseadas em listas encadeadas que possuem um nó superior também chamado de raiz que aponta para outros nós, chamados de nós filhos, que podem ser pais de outros nós.

Uma árvore de busca binária tem as seguintes propriedades:

- Todos os elementos na subárvore esquerda de um determinado nó n são menores que n;
- Todos os elementos na subárvore direita de um determinado nó n são maiores ou iguais a n.

![](https://arquivo.devmedia.com.br/artigos/Higor_Medeiros/ArvoreBinaria/ArvoreBinaria1.jpg)

No exemplo acima tem-se uma árvore binária onde a raiz é o elemento 8, o filho da esquerda do elemento 8 é o elemento 3, o filho da direita é o elemento número 10. Nota-se que todos elementos da árvore binária possuem no máximo dois filhos, sendo o da esquerda sempre menor e o da direita sempre maior que o elemento pai.

### Exemplo para inserção em árvores binárias.

````
public void inserir(No node, int valor) {
  //verifica se a árvore já foi criada
   if (node != null) {
    //Verifica se o valor a ser inserido é menor que o nodo corrente da árvore, se sim vai para subárvore esquerda
    if (valor < node.valor) {
        //Se tiver elemento no nodo esquerdo continua a busca
        if (node.esquerda != null) {
            inserir(node.esquerda, valor);
        } else {
            //Se nodo esquerdo vazio insere o novo nodo aqui
            System.out.println("  Inserindo " + valor + " a esquerda de " + node.valor);
            node.esquerda = new No(valor);
        }
    //Verifica se o valor a ser inserido é maior que o nodo corrente da árvore, se sim vai para subárvore direita
    } else if (valor > node.valor) {
        //Se tiver elemento no nodo direito continua a busca
        if (node.direita != null) {
            inserir(node.direita, valor);
        } else {
            //Se nodo direito vazio insere o novo nodo aqui
            System.out.println("  Inserindo " + valor + " a direita de " + node.valor);
            node.direita = new No(valor);
        }
    }
  }
}
````

## _Desempenho de uma árvore binária balanceada e outra não balanceada_ 

Uma árvore binária de busca depende da ordem da inserção para ter um tempo assintótico de busca ótimo, visto que o primeiro valor inserido será usado como uma raiz e os demais irão para esquerda ou para direita se forem maiores ou menores. Sendo assim, se você adicionar os valores em ordem crescente de s ficarão todos à direita do valor anterior, logo o tempo de busca será de O(n), sendo n o número de valores.
Já em uma árvore AVL isso não ocorre pois cada valor na árvore possui um dado que determina seu balanceamento baseado na altura do seu nó a direita menos a altura do seu nó a esquerda, lembrando que esses valores podem ser -1=<FB<=1.
Caso, após uma inserção qualquer valor da árvore fique com um fator de balanceamento diferente desses valores, a árvore se reestrutura mudando suas ligações para que todos os seus nós tenham esse fator de balanceamento. Sendo assim o tempo de busca assintótico ficará em torno de O independente da ordem de inserção dos valores.





 






