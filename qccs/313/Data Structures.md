# Data Structures I - CSCI 313

---



## 06/05 - Ch 3- Fundamental Data Structures

### Course Link https://bcs.wiley.com/he-bcs/Books?action=index&itemId=1118771338&bcsId=8635

### Basic Class Structure

* Ch3 - Introduction
* Ch 4, 5, 12, 13 - Algorithms
* Ch 6, 7 - Sequence Data Structures
* Ch 8, 9, 10, 11 - Trees
* Ch 14 - Graph Algorithms

Two types of data structures:

![image-20230605112934275](/Users/robles/repos/notes/qccs/313/Data Structures.assets/image-20230605112934275.png)

```java
public class SLList {
        /* Nest IntNode class into SLL, to create a full singly linked list */
        private static class IntNode {
            public int item;
            public IntNode next;

            public IntNode(int i, IntNode n) {
                item = i;
                next = n;
            }
        }
        //the first item (if it exists) is at sentinel.next
        private IntNode sentinel;
        //set the counter of size for linked list
        private int size;
        // Creates an empty SLList - instantiate a list w/ no ints
        public SLList() {
            sentinel = new IntNode(1, null);
            size = 0;
        }
        public SLList(int x) {
            sentinel = new IntNode(1, null);
            sentinel.next = new IntNode(x, null);
            size = 1;
        }
        public static void main(String[] args) {
            SLList L = new SLList(10); //creates new SLL with value 10 as first
            L.addFirst(10); //adds 10 to the first node
            L.addFirst(5); //adds node of 5 to first node, push everything back
            L.addLast(20); //appends 20 to end of the list
            
      		L.getFirst(); // output 5
     		L.size(); // output 4   
        }
    
    /* Linked List methods added to the class */
    
        //adds x to the front of the list
        public void addFirst(int x) {
            sentinel.next = new IntNode(x, sentinel.next);
            size += 1;
        }
        //returns first item in list
        public int getFirst() {
            return sentinel.next.item;
        }
    /*Adds an item to the end of the list */
    public void addLast(int x) {
        size += 1;
        IntNode p = sentinel;
        //Move p until it reaches the end of the list
        while (p.next != null) {
            p = p.next;
        }
        p.next = new IntNode(x, null);
    }
    //returns the size of the list
    public int size() {
        return size;
    }
}

```

