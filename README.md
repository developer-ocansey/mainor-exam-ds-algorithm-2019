# Exam EUAS 2019 Algorithms and data structures

Antonio Emmanuel Ocansey

## Describe Linked List and Queue

### Linked List

Linked list, this is a linear datastructure which contains series of nodes where each individual node contains both a value and a pointer to the next node in the list.

Some basic operation of linked list are 

Insertion (Add) grow the list by adding items to the end of the list.

Deletion (Remove) will always remove from a given position in the list.

Searching (Contains) will search the list for a value.

#### Example use cases:

Linked list is used for the implementation of Stacks and Queues

#### Sample Implementation

```
import java.io.*; 

public class LinkedList { 
  
    Node head;
  
    static class Node { 
  
        int data; 
        Node next; 

        Node(int d) 
        { 
            data = d; 
            next = null; 
        } 
    } 
    public static LinkedList insert(LinkedList list, int data) 
    { 
        Node new_node = new Node(data); 
        new_node.next = null; 

        if (list.head == null) { 
            list.head = new_node; 
        } 
        else { 
            Node last = list.head; 
            while (last.next != null) { 
                last = last.next; 
            } 
            last.next = new_node; 
        } 
  
        return list; 
    } 
    public static void printList(LinkedList list) 
    { 
        Node currNode = list.head; 
  
        System.out.print("\nLinkedList: "); 
        while (currNode != null) { 
            System.out.print(currNode.data + " "); 
  
            currNode = currNode.next; 
        } 
        System.out.println("\n"); 
    } 
  
    public static LinkedList deleteByKey(LinkedList list, int key) 
    { 
        Node currNode = list.head, prev = null; 

        if (currNode != null && currNode.data == key) { 
            list.head = currNode.next;
  
            System.out.println(key + " found and deleted"); 
  
            return list; 
        } 
        while (currNode != null && currNode.data != key) { 
            prev = currNode; 
            currNode = currNode.next; 
        } 
        if (currNode != null) { 
            prev.next = currNode.next; 
  
            System.out.println(key + " found and deleted"); 
        } 
  

  
        if (currNode == null) { 
            System.out.println(key + " not found"); 
        } 
  
        return list; 
    } 
  
    public static LinkedList deleteAtPosition(LinkedList list, int index) 
    { 
        Node currNode = list.head, prev = null; 
  
        if (index == 0 && currNode != null) { 
            list.head = currNode.next;
  
            System.out.println(index + " position element deleted"); 

            return list; 
        } 
   
        int counter = 0; 
  
        while (currNode != null) { 
  
            if (counter == index) { 
                prev.next = currNode.next; 
  
                System.out.println(index + " position element deleted"); 
                break; 
            } 
            else { 
                prev = currNode; 
                currNode = currNode.next; 
                counter++; 
            } 
        } 
  
        if (currNode == null) { 
            // Display the message 
            System.out.println(index + " position element not found"); 
        } 
  
        return list; 
    } 
  
    public static void main(String[] args) 
    { 
        LinkedList list = new LinkedList(); 
  
        // Insert the values 
        list = insert(list, 1); 
        list = insert(list, 2); 
        list = insert(list, 3); 
        list = insert(list, 4); 
        list = insert(list, 5); 
        list = insert(list, 6); 
        list = insert(list, 7); 
        list = insert(list, 8); 
  
        printList(list); 
  
        // Delete by key
        deleteByKey(list, 1); 

        printList(list); 
  
        deleteByKey(list, 4); 

        printList(list); 
  
        deleteByKey(list, 10); 

        printList(list); 
  
        //deletion  
        deleteAtPosition(list, 0); 
  
        printList(list); 
  
        deleteAtPosition(list, 2); 
  
        printList(list); 
  
        deleteAtPosition(list, 10); 

        printList(list); 
    } 
    // Source geeksforgeeks
}
```

### Queue

A Queue is a linear structure which follows a particular order in which the operations are performed. The order is First In First Out (FIFO). 
A good example of a queue is any queue of consumers for a resource where the consumer that came first is served first. The difference between stacks and queues is in removing. In a stack we remove the item the most recently added; in a queue, we remove the item the least recently added.

````
import java.util.*; 
  
class Imple  
{  
static class Queue  
{  
    static Stack<Integer> s1 = new Stack<Integer>();  
    static Stack<Integer> s2 = new Stack<Integer>();  
  
    static void enQueue(int x)  
    {  
        while (!s1.isEmpty()) 
        {  
            s2.push(s1.pop());  
        }  
  
        s1.push(x);  
  
        while (!s2.isEmpty())  
        {  
            s1.push(s2.pop());  
        }  
    }  
  
    static int deQueue()  
    {  
        if (s1.isEmpty())  
        {  
            System.out.println("Q is Empty");  
            System.exit(0);  
        }  
  
        int x = s1.peek();  
        s1.pop();  
        return x;  
    }  
};  
  
public static void main(String[] args)  
{  
    Queue q = new Queue();  
    q.enQueue(1);  
    q.enQueue(2);  
    q.enQueue(3);  
  
    System.out.println(q.deQueue());  
    System.out.println(q.deQueue()); 
    System.out.println(q.deQueue()); 
}  
}  
  
// Source geeksforgeeks

````



## Complexity of Algorithms O(N) meaning and examples

Complexity of an Algorithms is a measure which evaluates the order of the count of operations, performed by a given or algorithm as a function of the size of the input data.
O(n) represents the complexity of a function that increases linearly and in direct proportion to the number of inputs. This is a good example of how Big O Notation describes the worst case scenario as the function could return the true after reading the first element or false after reading all n elements.


#### Examples
````
public boolean containsNumber(List<Integer> numbers, int comparisonNumber) {
  for(Integer number : numbers) {
    if(number == comparisonNumber) {
      return true;
    }
  }
  return false;
}
````

