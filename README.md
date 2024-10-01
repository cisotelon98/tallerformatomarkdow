# Comparativo de codigos nodos

En este comparativo Andres molina y carlos sotelo escogieron los libros Koffman, Elliot B.; Wolfgang, Paul A. T. Data structures : abstraction and design using Java. Wiley 2016. Capítulo 2.5, página 77.  y  libros Michael T. Goodrich, Roberto Tamassia, Michael H. Goldwasser. Data Structures and Algorithms in Java. Wiley 2014. Capítulo 3.2, página 122.. respectivamente.

Compilamos y comparamos los codigos opteninedo como resultado lo siguiente:
## Estructura General
#### SinglyLinkedList

* Contiene nodos que tienen un solo enlace hacia el siguiente nodo (lista enlazada simple).
* Tiene un método para obtener el primer y último elemento, así como métodos para
* agregar y eliminar elementos.
#### MyLinkedList
* También es una lista enlazada simple, pero incluye la opción de agregar elementos en cualquier índice.
* Implementa la interfaz Iterable, lo que permite iterar sobre los elementos de la lista con un Iterator.

## Ventajas
#### SinglyLinkedList

+ Simplicidad: Es más simple y directa en su diseño.
 + Menos código: Al no incluir un método para agregar en un índice específico, el código es más corto.
#### MyLinkedList

* Flexibilidad: Permite agregar y eliminar elementos en cualquier índice.
* Iterabilidad: La implementación de Iterable facilita la iteración sobre los elementos de la lista, lo que puede ser muy útil en muchos contextos.
* Método toString(): Proporciona una representación textual de la lista, lo que puede ser útil para depuración y visualización.

## Desventajas
#### SinglyLinkedList
* Funcionalidad Limitada: No permite insertar elementos en posiciones específicas.
* No iterable: No implementa la interfaz Iterable, lo que puede hacer que la iteración sea menos conveniente.
#### MyLinkedList

* Complejidad: Más métodos y lógica que pueden llevar a una mayor posibilidad de errores.
* Rendimiento: El método add(int index, E e) tiene un rendimiento O(n) en el peor de los casos debido a la necesidad de recorrer la lista.
Markdown es un lenguaje de marcado que permite redactar cualquier tipo de documento sin depender del formato aplicado por ciertos editores en concreto.
## Métodos
#### SinglyLinkedList

* addFirst(E e): Agrega un elemento al inicio.
* addLast(E e): Agrega un elemento al final.
* removeFirst(): Elimina y retorna el primer elemento.
* first(), last(), size(), isEmpty(): Métodos de acceso simples.
#### MyLinkedList

* addFirst(E e): Similar a SinglyLinkedList.
* addLast(E e): Similar a SinglyLinkedList.
* add(int index, E e): Agrega un elemento en un índice específico.
* removeFirst(), removeLast(), remove(int index): Métodos para eliminar elementos en diferentes contextos.
* clear(): Limpia la lista.
## Diferencias en Implementación
#### Manejo de Nodos:

Ambas clases tienen una clase interna Node, pero MyLinkedList es un poco más flexible en su uso debido a su método para insertar en cualquier índice.
#### Métodos de Eliminación:

MyLinkedList tiene métodos para eliminar el último nodo y uno basado en índice, lo que añade versatilidad.
#### Iteración:

MyLinkedList implementa Iterator, lo que permite un uso más intuitivo en bucles.

## Conclusión
Ambas implementaciones son listas enlazadas simples, pero MyLinkedList ofrece más funcionalidad y flexibilidad a costa de mayor complejidad. La elección entre ellas dependerá del caso de uso: si solo se necesita una lista simple con operaciones básicas, SinglyLinkedList podría ser suficiente; si se requieren operaciones más complejas, MyLinkedList sería la mejor opción.



| | | | | | | | | | | | | | | | | |
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
| | | | | | | | | | | | | | | | | |
| | | | | |Libros|Michael T. Goodrich, Roberto Tamassia, Michael H. Goldwasser. Data Structures and Algorithms in Java. Wiley 2014. Capítulo 3.2, página 122.| | |Y. Daniel Liang - Introduction to Java Programming and Data Structures, Comprehensive Version-Addison Wesley (2019).pdf| | | | | | | |
| | | | | |Estructura|Listas simples|Listas circulares|Listas dobles enlazadas|listas | | |Ventajas 1|Desventajas 1|Ventajas 2|Desventajas 2|diferencias|
| | | | | |Node|Algorithm addFirst(e): newest = Node(e)  element e} newest.next =  head = newest  size = size+1| | |Node current = head;   while (current != null) {  System.out.println(current.element);  current = current.next; 5 }| | |acceso a todos los elementos , es simple y no modifica la lista|el código no permite modificación de la lista| | | |
| | | | | |addFirst|addFirst(e)| | |addFirst(E e)| | |acceso a todos los elementos , es simple y no modifica la lista| | | | |
| | | | | |addLast| addLast(e):  newest = Node(e) newest.next = null   tail.next = newest   tail = newest  size = size+1| | | public void addLast(E e) {   Node newNode = new Node<>(e);    if (tail == null) {   head = tail = newNode;   else {   tail.next = newNode;  tail = newNode;   }   size++;  }| | |simplicidad y eficiencia |dependencias y mal manejo de memoria|permite el manejo de listas vacías y lógica mas fácil de seguir|código con mas complejidad|complejidad de código y funcionamiento en listas vacías|
| | | | | |removeFirst|removeFirst( ):  if head == null then  the list is empty.  head = head.next  size = size−1| | |public E removeFirst() { 2  if (size == 0) return null;   else {  Node temp = head;   head = head.next;    size−−;    if (head == null) tail = null;  return temp.element;   }  }| | |simplicidad, eficiencia y código mas corto|no devuelve elementos eliminados, no muestra un valor si la lista esta vacía|devuelve muy en caso de lista vacía, actualiza y retorna elemento eliminado |mas complejo |complejidad de código y funcionan según requerimiento|
| | | | | |removeLast| | |E removeLast( ) {   if (isEmpty( )) return null;   return remove(trailer.getPrev( ));  }|public E removeLast() {   if (size == 0 "|"| size == 1) {  return removeFirst();   }   else {  Node current = head;   for (int i = 0; i < size − 2; i++) {  current = current.next;  }   E temp = tail.element;   tail = current;   tail.next = null;  size−−;  return temp;   }  }| | |simplicidad, eficiencia y código mas corto y no recorre la lista |depende de otros métodos |permite la coherencia en caso de que la lista tenga 1 o 0 además de manejar el acceso directo a nodos. |mayor complejidad |manejas métodos de eliminación diferentes ,cada uno se preocupa por las lista de tamaño|
| | | | | |rotate( )| |public void rotate( ) {   if (tail != null) // if empty, do nothing  tail = tail.getNext( );   }| | | | |código directo y fácil de entender, permite un rotación de la estructura|si la estructura no esta bien puede no retornar valor  ni tener lógica de circularidad| | |En esta caso solo un libro tenia este tipo de listas|
| | | | | |isEmpty| | |isEmpty( ) { return size == 0; }    public E first( ) {  if (isEmpty( )) return null;  return header.getNext( ).getElement( );  }| | | |simplicidad, claridad del código y rendimiento|tiene dependencias de tamaño y es muy como flexible| | |En esta caso solo un libro tenia este tipo de listas|
| | | | | |E last| | |E last( ) {   if (isEmpty( )) return null;  return trailer.getPrev( ).getElement( );   }| | | |simplicidad, encapsulamiento|depende de un estructura interna, falta de documentación de debe asegurar que le método este bien probado | | |En esta caso solo un libro tenia este tipo de listas|
