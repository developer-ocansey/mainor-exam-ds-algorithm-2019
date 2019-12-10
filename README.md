# Exam for EUAS 2019 Algorithms and data structures

Antonio Emmanuel Ocansey

## Describe Linked List and Queue

### Linked List

Linked list, this is a linear datastructure which contains series of nodes where each individual node contains both a value and a pointer to the next node in the list.

Some basic operation of linked list are 

Insertion (Add) grow the list by adding items to the end of the list.

Deletion (Remove) will always remove from a given position in the list.

Searching (Contains) will search the list for a value.

Example use cases:

Linked list is used for the implementation of Stacks and Queues

Sample Implementation

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
            list.head = currNode.next; // Changed head 
  
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
            list.head = currNode.next; // Changed head 
  
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
        /* Start with the empty list. */
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
}
```

### Queue

What things you need to install the software and how to install them


## Complexity of Algorithms O(N) meaning and examples

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.