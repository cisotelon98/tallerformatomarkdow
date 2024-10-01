# Comparativo de codigos nodos

En este comparativo Andres molina y carlos sotelo escogieron los Koffman, Elliot B.; Wolfgang, Paul A. T. Data structures : abstraction and design using Java. Wiley 2016. Capítulo 2.5, página 77.  y  libros Michael T. Goodrich, Roberto Tamassia, Michael H. Goldwasser. Data Structures and Algorithms in Java. Wiley 2014. Capítulo 3.2, página 122.. respectivamente.

Compilamos y comparamos los codigos opteninedo como resultado lo siguiente:
## Estructura General
#### SinglyLinkedList

* Contiene nodos que tienen un solo enlace hacia el siguiente nodo (lista enlazada simple).
* Tiene un método para obtener el primer y último elemento, así como métodos para agregar y eliminar elementos.
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
* terator(): Permite iterar sobre la lista.

## Diferencias en Implementación
#### Manejo de Nodos:

Ambas clases tienen una clase interna Node, pero MyLinkedList es un poco más flexible en su uso debido a su método para insertar en cualquier índice.
#### Métodos de Eliminación:

MyLinkedList tiene métodos para eliminar el último nodo y uno basado en índice, lo que añade versatilidad.
#### Iteración:

MyLinkedList implementa Iterator, lo que permite un uso más intuitivo en bucles.

## Conclusión
Ambas implementaciones son listas enlazadas simples, pero MyLinkedList ofrece más funcionalidad y flexibilidad a costa de mayor complejidad. La elección entre ellas dependerá del caso de uso: si solo se necesita una lista simple con operaciones básicas, SinglyLinkedList podría ser suficiente; si se requieren operaciones más complejas, MyLinkedList sería la mejor opción.


| | | | | | | | | | | | | | | | |
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
| | | | |Libros|Michael T. Goodrich, Roberto Tamassia, Michael H. Goldwasser. Data Structures and Algorithms in Java. Wiley 2014. Capítulo 3.2, página 122.| | |Y. Daniel Liang - Introduction to Java Programming and Data Structures, Comprehensive Version-Addison Wesley (2019).pdf| | | | | | | |
| | | | |Estructura|Listas simples|Listas circulares|Listas dobles enlazadas|listas | | |Ventajas 1|Desventajas 1|Ventajas 2|Desventajas 2|diferencias|
| | | | |Node|Algorithm addFirst(e): newest = Node(e)  element e} newest.next =  head = newest  size = size+1| | |Node current = head;   while (current != null) {  System.out.println(current.element);  current = current.next; 5 }| | |acceso a todos los elementos , es simple y no modifica la lista|el código no permite modificación de la lista| | | |
| | | | |addFirst|addFirst(e)| | |addFirst(E e)| | |acceso a todos los elementos , es simple y no modifica la lista| | | | |
| | | | |addLast| addLast(e):  newest = Node(e) newest.next = null   tail.next = newest   tail = newest  size = size+1| | | public void addLast(E e) {   Node newNode = new Node<>(e);    if (tail == null) {   head = tail = newNode;   else {   tail.next = newNode;  tail = newNode;   }   size++;  }| | |simplicidad y eficiencia |dependencias y mal manejo de memoria|permite el manejo de listas vacías y lógica mas fácil de seguir|código con mas complejidad|complejidad de código y funcionamiento en listas vacías|
| | | | |removeFirst|removeFirst( ):  if head == null then  the list is empty.  head = head.next  size = size−1| | |public E removeFirst() { 2  if (size == 0) return null;   else {  Node temp = head;   head = head.next;    size−−;    if (head == null) tail = null;  return temp.element;   }  }| | |simplicidad, eficiencia y código mas corto|no devuelve elementos eliminados, no muestra un valor si la lista esta vacía|devuelve muy en caso de lista vacía, actualiza y retorna elemento eliminado |mas complejo |complejidad de código y funcionan según requerimiento|
| | | | |removeLast| | |E removeLast( ) {   if (isEmpty( )) return null;   return remove(trailer.getPrev( ));  }|public E removeLast() {   if (size == 0 "|"| size == 1) {  return removeFirst();   }   else {  Node current = head;   for (int i = 0; i < size − 2; i++) {  current = current.next;  }   E temp = tail.element;   tail = current;   tail.next = null;  size−−;  return temp;   }  }| | |simplicidad, eficiencia y código mas corto y no recorre la lista |depende de otros métodos |permite la coherencia en caso de que la lista tenga 1 o 0 además de manejar el acceso directo a nodos. |mayor complejidad |manejas métodos de eliminación diferentes ,cada uno se preocupa por las lista de tamaño|
| | | | |rotate( )| |public void rotate( ) {   if (tail != null) // if empty, do nothing  tail = tail.getNext( );   }| | | | |código directo y fácil de entender, permite un rotación de la estructura|si la estructura no esta bien puede no retornar valor  ni tener lógica de circularidad| | |En esta caso solo un libro tenia este tipo de listas|
| | | | |isEmpty| | |isEmpty( ) { return size == 0; }    public E first( ) {  if (isEmpty( )) return null;  return header.getNext( ).getElement( );  }| | | |simplicidad, claridad del código y rendimiento|tiene dependencias de tamaño y es muy como flexible| | |En esta caso solo un libro tenia este tipo de listas|
| | | | |E last| | |E last( ) {   if (isEmpty( )) return null;  return trailer.getPrev( ).getElement( );   }| | | |simplicidad, encapsulamiento|depende de un estructura interna, falta de documentación de debe asegurar que le método este bien probado | | |En esta caso solo un libro tenia este tipo de listas|

## Codigos carlos :
### lista simplemente enlazada
public class SinglyLinkedList<E> {
//---------------- nested Node class ----------------
private static class Node<E> {
private E element; // reference to the element stored at this node
private Node<E> next; // reference to the subsequent node in the list
public Node(E e, Node<E> n) {
element = e;
next = n;
}
 public E getElement( ) { return element; }
    public Node<E> getNext( ) { return next; }
    public void setNext(Node<E> n) { next = n; }
     } //----------- end of nested Node class -----------
  
        // instance variables of the SinglyLinkedList
        private Node<E> head = null; // head node of the list (or null if empty)
         private Node<E> tail = null; // last node of the list (or null if empty)
        private int size = 0; // number of nodes in the list
        public SinglyLinkedList( ) { } // constructs an initially empty list
        // access methods
        public int size( ) { return size; }
        public boolean isEmpty( ) { return size == 0; }
        public E first( ) { // returns (but does not remove) the first element
        if (isEmpty( )) return null;
         return head.getElement( );
         }
         public E last( ) { // returns (but does not remove) the last element
         if (isEmpty( )) return null;
         return tail.getElement( );
         }
         // update methods
        public void addFirst(E e) { // adds element e to the front of the list
        head = new Node<>(e, head); // create and link a new node
         if (size == 0)
         tail = head; // special case: new node becomes tail also
         size++;
         }
         public void addLast(E e) { // adds element e to the end of the list
         Node<E> newest = new Node<>(e, null); // node will eventually be the tail
         if (isEmpty( ))
         head = newest; // special case: previously empty list
         else
         tail.setNext(newest); // new node after existing tail
         tail = newest; // new node becomes the tail
         size++;
         }
         public E removeFirst() { // removes and returns the first element
            if (isEmpty()) return null; // nothing to remove
            E answer = head.getElement();
            head = head.getNext(); // will become null if list had only one node
            size--; // Cambia size−− por size--
            if (size == 0)
                tail = null; // special case as list is now empty
            return answer;
        }
}
public class Main {
    public static void main(String[] args) {
        SinglyLinkedList<Integer> list = new SinglyLinkedList<>();

        // Agregar elementos
        list.addLast(1);
        list.addLast(2);
        list.addFirst(0);

        // Imprimir el tamaño
        System.out.println("Tamaño de la lista: " + list.size()); // Debería ser 3

        // Obtener el primer y último elemento
        System.out.println("Primer elemento: " + list.first()); // Debería ser 0
        System.out.println("Último elemento: " + list.last());   // Debería ser 2

        // Remover el primer elemento
        list.removeFirst();
        System.out.println("Tamaño después de remover: " + list.size()); // Debería ser 2
        System.out.println("Nuevo primer elemento: " + list.first()); // Debería ser 1
    }
#### new Main().main(null);
#### Resultado :
Tamaño de la lista: 3
Primer elemento: 0
Último elemento: 2
Tamaño después de remover: 2
Nuevo primer elemento: 1
### lista circularmente enlazada
public class CircularlyLinkedList<E> {
    private static class Node<E> {
        private E element;
        private Node<E> next;

        public Node(E element, Node<E> next) {
            this.element = element;
            this.next = next;
        }

        public E getElement() {
            return element;
        }

        public Node<E> getNext() {
            return next;
        }

        public void setNext(Node<E> next) {
            this.next = next;
        }
    }

    private Node<E> tail = null; // we store tail (but not head)
    private int size = 0; // number of nodes in the list

    public CircularlyLinkedList() { } // constructs an initially empty list

    // access methods
    public int size() { return size; }
    public boolean isEmpty() { return size == 0; }
    
    public E first() { // returns (but does not remove) the first element
        if (isEmpty()) return null;
        return tail.getNext().getElement(); // the head is *after* the tail
    }
    
    public E last() { // returns (but does not remove) the last element
        if (isEmpty()) return null;
        return tail.getElement();
    }

    // update methods
    public void rotate() { // rotate the first element to the back of the list
        if (tail != null) // if empty, do nothing
            tail = tail.getNext(); // the old head becomes the new tail
    }

    public void addFirst(E e) { // adds element e to the front of the list
        if (size == 0) {
            tail = new Node<>(e, null);
            tail.setNext(tail); // link to itself circularly
        } else {
            Node<E> newest = new Node<>(e, tail.getNext());
            tail.setNext(newest);
        }
        size++;
    }

    public void addLast(E e) { // adds element e to the end of the list
        addFirst(e); // insert new element at front of list
        tail = tail.getNext(); // now new element becomes the tail
    }

    public E removeFirst() { // removes and returns the first element
        if (isEmpty()) return null; // nothing to remove
        Node<E> head = tail.getNext();
        if (head == tail) tail = null; // must be the only node left
        else tail.setNext(head.getNext()); // removes “head” from the list
        size--;
        return head.getElement();
    }
}

public class CircularlyLinkedListTest {
    public static void main(String[] args) {
        CircularlyLinkedList<Integer> list = new CircularlyLinkedList<>();

        // Agregar elementos
        System.out.println("Agregando elementos:");
        list.addLast(1);
        list.addLast(2);
        list.addLast(3);
        list.addFirst(0);

        // Mostrar elementos
        System.out.println("Tamaño de la lista: " + list.size());
        System.out.println("Primer elemento: " + list.first());
        System.out.println("Último elemento: " + list.last());

        // Rotar y mostrar
        list.rotate();
        System.out.println("Después de rotar:");
        System.out.println("Primer elemento: " + list.first());
        
        // Eliminar el primer elemento
        System.out.println("Eliminando el primer elemento: " + list.removeFirst());
        System.out.println("Nuevo primer elemento: " + list.first());
        System.out.println("Tamaño de la lista después de eliminar: " + list.size());
        
        // Mostrar todos los elementos restantes
        System.out.println("Elementos restantes en la lista:");
        while (!list.isEmpty()) {
            System.out.print(list.removeFirst() + " ");
        }
        System.out.println();
        System.out.println("Tamaño de la lista al final: " + list.size());
    }
}

#### new CircularlyLinkedListTest().main(null);
#### Resultado :
Agregando elementos:
Tamaño de la lista: 4
Primer elemento: 0
Último elemento: 3
Después de rotar:
Primer elemento: 1
Eliminando el primer elemento: 1
Nuevo primer elemento: 2
Tamaño de la lista después de eliminar: 3
Elementos restantes en la lista:
2 3 0 
Tamaño de la lista al final: 0

### lista doblemente enlazada
public class DoublyLinkedList<E> {
    //---------------- nested Node class ----------------
    private static class Node<E> {
        private E element; // reference to the element stored at this node
        private Node<E> prev; // reference to the previous node in the list
        private Node<E> next; // reference to the subsequent node in the list

        public Node(E e, Node<E> p, Node<E> n) {
            element = e;
            prev = p;
            next = n;
        }

        public E getElement() { return element; }
        public Node<E> getPrev() { return prev; }
        public Node<E> getNext() { return next; }
        public void setPrev(Node<E> p) { prev = p; }
        public void setNext(Node<E> n) { next = n; }
    } //----------- end of nested Node class -----------

    // instance variables of the DoublyLinkedList
    private Node<E> header; // header sentinel
    private Node<E> trailer; // trailer sentinel
    private int size = 0; // number of elements in the list

    /** Constructs a new empty list. */
    public DoublyLinkedList() {
        header = new Node<>(null, null, null); // create header
        trailer = new Node<>(null, header, null); // trailer is preceded by header
        header.setNext(trailer); // header is followed by trailer
    }

    /** Returns the number of elements in the linked list. */
    public int size() { return size; }

    /** Tests whether the linked list is empty. */
    public boolean isEmpty() { return size == 0; }

    /** Returns (but does not remove) the first element of the list. */
    public E first() {
        if (isEmpty()) return null;
        return header.getNext().getElement(); // first element is beyond header
    }

    /** Returns (but does not remove) the last element of the list. */
    public E last() {
        if (isEmpty()) return null;
        return trailer.getPrev().getElement(); // last element is before trailer
    }

    // public update methods
    /** Adds element e to the front of the list. */
    public void addFirst(E e) {
        addBetween(e, header, header.getNext()); // place just after the header
    }

    /** Adds element e to the end of the list. */
    public void addLast(E e) {
        addBetween(e, trailer.getPrev(), trailer); // place just before the trailer
    }

    /** Removes and returns the first element of the list. */
    public E removeFirst() {
        if (isEmpty()) return null; // nothing to remove
        return remove(header.getNext()); // first element is beyond header
    }

    /** Removes and returns the last element of the list. */
    public E removeLast() {
        if (isEmpty()) return null; // nothing to remove
        return remove(trailer.getPrev()); // last element is before trailer
    }

    // private update methods
    /** Adds element e to the linked list in between the given nodes. */
    private void addBetween(E e, Node<E> predecessor, Node<E> successor) {
        // create and link a new node
        Node<E> newest = new Node<>(e, predecessor, successor);
        predecessor.setNext(newest);
        successor.setPrev(newest);
        size++;
    }

    /** Removes the given node from the list and returns its element. */
    private E remove(Node<E> node) {
        Node<E> predecessor = node.getPrev();
        Node<E> successor = node.getNext();
        predecessor.setNext(successor);
        successor.setPrev(predecessor);
        size--;
        return node.getElement();
    }
}
    public class DoublyLinkedListTest {
    public static void main(String[] args) {
        // Crear una instancia de DoublyLinkedList
        DoublyLinkedList<Integer> list = new DoublyLinkedList<>();

        // Agregar elementos
        System.out.println("Agregando elementos:");
        list.addLast(10);
        list.addLast(20);
        list.addFirst(5);

        // Mostrar el tamaño y los elementos
        System.out.println("Tamaño de la lista: " + list.size());
        System.out.println("Primer elemento: " + list.first());
        System.out.println("Último elemento: " + list.last());

        // Eliminar el primer elemento
        System.out.println("Eliminando el primer elemento: " + list.removeFirst());
        System.out.println("Nuevo primer elemento: " + list.first());
        System.out.println("Tamaño de la lista después de eliminar: " + list.size());

        // Eliminar el último elemento
        System.out.println("Eliminando el último elemento: " + list.removeLast());
        System.out.println("Tamaño de la lista al final: " + list.size());

        // Agregar más elementos
        list.addLast(30);
        list.addLast(40);
        System.out.println("Tamaño de la lista después de agregar más elementos: " + list.size());
        
        // Mostrar todos los elementos restantes
        System.out.println("Elementos restantes en la lista:");
        while (!list.isEmpty()) {
            System.out.print(list.removeFirst() + " ");
        }
        System.out.println();
        System.out.println("Tamaño de la lista al final: " + list.size());
    }
}

#### new DoublyLinkedListTest().main(null);

#### Resultado :
Agregando elementos:
Tamaño de la lista: 3
Primer elemento: 5
Último elemento: 20
Eliminando el primer elemento: 5
Nuevo primer elemento: 10
Tamaño de la lista después de eliminar: 2
Eliminando el último elemento: 20
Tamaño de la lista al final: 1
Tamaño de la lista después de agregar más elementos: 3
Elementos restantes en la lista:
10 30 40 
Tamaño de la lista al final: 0



