# Linked List Codes

```java
/*
import java.lang.*;
import java.util.*;

public class LinkedList {

    static Scanner sc = new Scanner(System.in);
    public static int N;
    public static Node H;

    int data;
    Node next;
    LinkedList (int x) {

        data = x;
        next = null;
    }

    public static void printList() {

        System.out.print("The elements of the linked list are : ");
        Node T = H;
        int count = 0;
        while (T != null) {

            count++;
            if (count == N) {

                System.out.print(T.data);
            }
            else {

                System.out.print(T.data + " -> ");
            }
            T = T.next;
        }
        System.out.println(" ");
    }

    public static void getSize() {

        Node T = H;
        int count = 0;
        while (T != null) {

            count++;
            T = T.next;
        }
        System.out.println("The size of the linked list is : " + count);
    }

    public static void kthNode() {

        System.out.println("Enter the value of k : ");
        int k = sc.nextInt();
        Node T = H;
        int count = 0;
        int f = 0;
        while (T != null) {

            count++;
            if (k == count) {

                System.out.println("The element at kth position is : " + T.data);
                f++;
                break;
            }
            T = T.next;
        }
        if (f == 0) {

            System.out.println("kth node out of bound");
        }
    }

    public static void searchList() {

        System.out.println("Enter the element to search : ");
        int key = sc.nextInt();
        Node T = H;
        int count = 0;
        int f = 0;
        while (T != null) {

            count++;
            if (T.data == key) {

                System.out.println("Element found at " + count + " position");
                f++;
            }
            T = T.next;
        }
        if (f == 0) {

            System.out.println("Element not found");
        }
    }

    public static void insertNode(int p, int x) {

        Node X = H;

        if (p == 0) {

            Node Z = new Node(x);
            Z.next = H;
            H = Z;
        }
        else {

            for (int i = 0; i < p - 1; i++) {

                X = X.next;
            }

            Node Y = X.next;
            Node Z = new Node(x);
            X.next = Z;
            Z.next = Y;
        }
        N++;
    }

    public static void reverse (Node T) {

        if (T == null) return;
        reverse(T.next);
        System.out.print(T.data + " -> ");
    }

    public static void deleteNode(int p) {

        Node X = H;
        if (p == 0) {

            H = H.next;
        }
        for (int i = 0; i < p - 1; i++) {

            X = X.next;
        }
        X.next = X.next.next;
        N--;
    }

    public static void deleteValue(int x) {

        Node X = H;
        Node Y = H;

        if (X.data == x) {

            H = X.next;
        }
        while (X != null && X.data != x) {

            Y = X;
            X = X.next;
        }
        Y.next = X.next;

        N--;
    }

    public static void main (String[] args) {

        System.out.println("Enter size of linked list : ");
        N = sc.nextInt();

        System.out.println("Enter elements : ");
        H = new Node(sc.nextInt());
        Node T = H;
        for (int i = 1; i < N; i++) {

            T.next = new Node(sc.nextInt());
            T = T.next;
        }
        printList();

        System.out.println("""
                
                 1. Find the Size of the Linked List\
                
                 2. Print the Kth Node in the Linked List\
                
                 3. Search if Node with Value x Present in the Linked List\
                
                 4. Print the Linked List in Reverse Order by Using Recursion\
                
                 5. Insert a Node with Value x in the Beginning of the Linked List\
                
                 6. Insert a Node with Value x in the Middle of Linked List\
                
                 7. Insert a Node with Value x and Position p in the Linked List\
                
                 8. Insert a Node with Value v in the End of the Linked List\
                
                 9. Delete a Node in the Beginning of the Linked List\
                
                 10. Delete a Node in the Middle of the Linked List\
                
                 11. Delete a Node with Value x in the Linked List\
                
                 12. Delete a Node at Position p in the Linked List\
                
                 13. Delete the Last Node in the Linked List\
                """);

        int cont;
        do {

            System.out.println("Enter an option : ");
            int choice = sc.nextInt();

            switch (choice) {

                case 1 :
                {
                    getSize();
                    break;
                }
                case 2 :
                {
                    kthNode();
                    break;
                }
                case 3 :
                {
                    searchList();
                    break;
                }
                case 4 :
                {
                    System.out.println("Reverse order of the elements : ");
                    T = H;
                    reverse(T);
                    break;
                }
                case 5 :
                {
                    int p = 0;
                    System.out.println("Enter value of the element : ");
                    int x = sc.nextInt();
                    insertNode(p, x);
                    printList();
                    break;
                }
                case 6 :
                {
                    int mid = (N - 1) / 2;
                    System.out.println("Enter value of the element : ");
                    int x = sc.nextInt();
                    insertNode(mid, x);
                    printList();
                    break;
                }
                case 7 :
                {
                    System.out.println("Enter the position to insert the node : ");
                    int p = sc.nextInt();
                    System.out.println("Enter value of the element : ");
                    int x = sc.nextInt();
                    insertNode(p, x);
                    printList();
                    break;
                }
                case 8 :
                {
                    int p = N;
                    System.out.println("Enter value of the element : ");
                    int x = sc.nextInt();
                    insertNode(p, x);
                    printList();
                    break;
                }
                case 9 :
                {
                    int p = 0;
                    deleteNode(p);
                    printList();
                    break;
                }
                case 10 :
                {
                    int mid = (N - 1) / 2;
                    deleteNode(mid);
                    printList();
                    break;
                }
                case 11 :
                {
                    System.out.println("Enter value of the element to delete : ");
                    int x = sc.nextInt();
                    deleteValue(x);
                    printList();
                    break;
                }
                case 12 :
                {
                    System.out.println("Enter the position to delete the node : ");
                    int p = sc.nextInt();
                    deleteNode(p);
                    printList();
                    break;
                }
                case 13 :
                {
                    int p = N - 1;
                    deleteNode(p);
                    printList();
                    break;
                }
                default :
                {
                    System.out.println("Enter a valid option");
                }
            }
            System.out.println("Do you wish to continue? 0 - continue, 1 - stop");
            cont = sc.nextInt();
        } while(cont == 0);
    }
}
*/
