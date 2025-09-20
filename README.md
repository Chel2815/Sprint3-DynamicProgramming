# Sprint 3 Dynamic Programming

## Explicação do código

_Análise de Consumo de Insumos_

Este projeto em Python demonstra a aplicação de estruturas de dados e algoritmos clássicos para gerenciar e analisar o consumo de insumos, como reagentes de laboratório. A aplicação utiliza filas, pilhas, e algoritmos de busca e ordenação para manipular os dados de forma eficiente.

------------------------------

_Classes e Estruturas de Dados_

*Insumo*
A classe Insumo representa um item individual com as seguintes propriedades:

nome: Nome do insumo (ex: "Reagente A").

quantidade: Quantidade disponível.

validade: Data de validade no formato 'YYYY-MM-DD', o que permite a ordenação cronológica.

*Consumo*
A classe Consumo gerencia o fluxo de entrada e consulta de insumos usando duas estruturas de dados fundamentais:

Fila (self.fila): Implementada com collections.deque, a fila segue o princípio FIFO (First-In, First-Out). Isso significa que o primeiro item a ser adicionado é o primeiro a ser processado. No contexto deste código, a fila mantém o registro dos insumos na ordem em que foram consumidos, permitindo uma visualização cronológica do consumo.

Pilha (self.pilha): A pilha é uma lista que opera no princípio LIFO (Last-In, First-Out). O último item adicionado é o primeiro a ser removido. Aqui, a pilha armazena o histórico de consumo, sendo útil para desfazer operações ou para visualizar as consultas mais recentes de forma rápida.

------------------------------

_Algoritmos de Busca_

O código inclui duas implementações de algoritmos de busca para localizar um insumo na lista.

*Busca Sequencial (busca_sequencial)*

Este algoritmo percorre a lista item por item do início ao fim até encontrar o insumo desejado ou até que a lista termine. É um método simples e direto, mas sua eficiência é baixa para listas muito grandes, com uma complexidade de tempo de O(n), onde n é o número de itens na lista.

*Busca Binária (busca_binaria)*

Este é um algoritmo de busca muito mais eficiente, com uma complexidade de tempo de O(log n). No entanto, ele tem uma exigência crucial: a lista deve estar previamente ordenada. Ele funciona dividindo repetidamente a lista pela metade para encontrar o item. Se o item do meio for o que você procura, a busca termina. Se não, o algoritmo descarta a metade da lista onde o item não pode estar e continua a busca na metade restante.

------------------------------

_Algoritmos de Ordenação_

Para que a busca binária seja eficaz e para outras análises de dados, o código utiliza dois algoritmos clássicos de ordenação.

*Merge Sort (merge_sort)*

O Merge Sort é um algoritmo de ordenação do tipo "dividir para conquistar". Ele divide a lista recursivamente em sublistas menores até que cada sublista tenha apenas um elemento. Em seguida, ele "mescla" (merge) essas sublistas de volta em uma única lista ordenada. É um algoritmo estável e eficiente, com uma complexidade de tempo de O(n log n).

*Quick Sort (quick_sort)*

O Quick Sort também é um algoritmo de "dividir para conquistar" e geralmente é considerado um dos mais rápidos na prática. Ele funciona escolhendo um elemento chamado pivô e particionando a lista em três grupos: elementos menores que o pivô, elementos iguais ao pivô e elementos maiores que o pivô. Em seguida, ele aplica a mesma lógica recursivamente aos grupos de "menores" e "maiores" até que toda a lista esteja ordenada. A complexidade de tempo média é O(n log n).

Execução *(if __name__ == "__main__":)*

A seção de execução demonstra o uso de todas as classes e funções:

Registro de Consumo: Quatro insumos são registrados, e a ordem de registro é mantida pela fila (consumo.mostrar_fila()).

Visualização da Pilha: A pilha é mostrada em ordem inversa de registro, refletindo a natureza LIFO.

Buscas:

busca_sequencial localiza "Reagente B" na lista original.

A lista é ordenada por nome usando merge_sort para que a busca_binaria possa ser realizada com sucesso para encontrar "Reagente C".

Ordenações:

A lista de insumos é ordenada por quantidade usando merge_sort.

A lista é ordenada por validade usando quick_sort.

