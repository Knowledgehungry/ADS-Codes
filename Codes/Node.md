```java

/*
import java.lang.*;
import java.util.*;

public class Node {

    Node next;
    int data;
    Node LP, RP;

    Node (int x) {

        data = x;
        LP = null;
        RP = null;
    }

    public static int size(Node R) {

        if (R == null) {

            return 0;
        }
        int l = size(R.LP);
        int r = size(R.RP);
        return (l + r + 1);
    }

    public static boolean checkIfBST(Node R, int s, int e) {

        if (R == null) return true;

        if (R.data < s || R.data > e) return false;

        return checkIfBST(R.LP, s, R.data - 1) && checkIfBST(R.RP, R.data + 1, e);
    }

    public static void checkIf(Node R, int k) {

        Node T = R;
        int c = 0;
        while (T != null) {

            if (T.data == k) {

                System.out.println("Found");
                c++;
                break;
            }
            else if (T.data > k) {

                T = T.LP;
            }
            else {

                T = T.RP;
            }
        }
        if (c == 0) {

            System.out.println("Not found");
        }
    }

    public static void checkPrTT (int[] A) {

        int start = Integer.MIN_VALUE;
        int end = Integer.MAX_VALUE;
        int R = A[0];
        int N = A.length;
        int c = 0;
        for (int i = 1; i < N; i++) {

            if (A[i] > R) {

                start = R + 1;
            }
            else {

                end = R - 1;
            }
            if (A[i] < start || A[i] > end) {

                System.out.println("No");
                c++;
            }
            R = A[i];
        }
        if (c == 0) {

            System.out.println("Yes");
        }
    }

    static class Index {
        int i = 0;
    }

    public static void ITT(Node R, int[] A, Index i) {

        if (R == null) return;
        ITT(R.LP, A, i);
        A[i.i++] = R.data;
        ITT(R.RP, A, i);
    }

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);
        Node R = new Node(12);
        R.LP = new Node(5);
        R.LP.LP = new Node(2);
        R.LP.RP = new Node(10);
        R.LP.RP.LP = new Node(6);
        R.LP.RP.LP.RP = new Node(8);
        R.LP.RP.LP.RP.LP = new Node(7);
        R.LP.RP.LP.RP.RP = new Node(9);
        R.RP = new Node(20);
        R.RP.RP = new Node(22);
        R.RP.RP.LP = new Node(21);
        R.RP.RP.RP = new Node(25);

        int cnt = 0;
        do {

            System.out.println("Enter command : ");
            String s = sc.next();

            if (s.equals("checkIfBST")) {

                int start = Integer.MIN_VALUE;
                int end = Integer.MAX_VALUE;
                System.out.println("Is the given tree a binary search tree? - " + checkIfBST(R, start, end));
            }
            else if (s.startsWith("checkIf")) {

                int k = Integer.parseInt(s.substring(s.indexOf('(') + 1, s.indexOf(')')));
                checkIf(R, k);
            }
            else if (s.equals("checkPrTT")) {

                int[] A = {4, 10, 5, 8};
                System.out.println("Is the preorder traversal a binary search tree? - ");
                checkPrTT(A);
            }
            else if (s.startsWith("find")) {

                int N = size(R);
                int[] A = new int[N];
                Index idx = new Index();
                int k = Integer.parseInt(s.substring(s.indexOf('(') + 1, s.indexOf(')')));

                ITT(R, A, idx);

                if (k >= 0 && k < N) {

                    System.out.println("kth smallest element in the binary search tree : " + A[k]);
                }
            }
            else {

                System.out.println("Enter definite command");
            }

            System.out.println();
            System.out.println("Do you wish to continue? 0 - continue 1 - stop");
            cnt = sc.nextInt();
        } while (cnt == 0);
    }
}
*/

/*

// Check Binary Search Tree
import java.lang.*;
import java.util.*;

public class Node {

    Node next;
    int data;
    Node LP, RP;

    Node(int x) {

        data = x;
        LP = null;
        RP = null;
    }

    public static boolean CBST (Node R, int s, int e) {

        if (R == null) return true;

        if (R.data < s || R.data > e) return false;

        boolean b = CBST(R.LP, s, R.data - 1) && CBST(R.RP, R.data + 1, e);
        return b;
    }

    public static void main (String[] args) {

        Node R = new Node(12);
        R.LP = new Node(5);
        R.LP.LP = new Node(2);
        R.LP.RP = new Node(10);
        R.LP.RP.LP = new Node(6);
        R.LP.RP.LP.RP = new Node(8);
        R.LP.RP.LP.RP.LP = new Node(7);
        R.LP.RP.LP.RP.RP = new Node(13);
        R.RP = new Node(20);
        R.RP.LP = new Node(21);
        R.RP.RP = new Node(22);
        R.RP.RP.RP = new Node(25);

        System.out.println(CBST(R, 2, 25));
    }
}
*/

/*

// Binary Search Assignment
import java.lang.*;
import java.util.*;

public class Node {

    public Node next;
    int data;
    Node LP, RP;
    Node (int x) {

        data = x;
        LP = null;
        RP = null;
    }

    public static int size(Node R) {

        if (R == null) {

            return 0;
        }
        int l = size(R.LP);
        int r = size(R.RP);
        return (l + r + 1);
    }

    public static void checkIf(Node R, int k) {

        Node T = R;
        int c = 0;
        while (T != null) {

            if (T.data == k) {

                System.out.println("Found");
                c++;
                break;
            }
            else if (T.data > k) {

                T = T.LP;
            }
            else {

                T = T.RP;
            }
        }
        if (c == 0) {

            System.out.println("Not found");
        }
    }

    public static void PrTT (Node R) {

        if (R == null) {
            return;
        }
        System.out.print(R.data + " ");
        PrTT(R.LP);
        PrTT(R.RP);
    }

    public static void ITT (Node R) {

        if (R ==  null) {
            return;
        }
        ITT(R.LP);
        System.out.print(R.data + " ");
        ITT(R.RP);
    }

    public static void PsTT (Node R){

        if (R == null) {
            return;
        }
        PsTT(R.LP);
        PsTT(R.RP);
        System.out.print(R.data + " ");
    }

    public static void levelOrder (Node R) {

        Queue<Node> q = new LinkedList<>();
        q.add(R);
        while (q.size() > 0) {

            int cs = q.size();
            for (int i = 1; i <= cs; i++) {

                Node tmp =  q.remove();
                System.out.print(tmp.data + " ");

                if (tmp.LP != null) {

                    q.add(tmp.LP);
                }
                if (tmp.RP != null) {

                    q.add(tmp.RP);
                }
            }
            System.out.println();
        }
    }

    public static void height(Node R) {

        Queue<Node> q = new LinkedList<>();
        q.add(R);
        int h = 0;
        while (q.size() > 0) {

            int cs = q.size();
            for (int i = 1; i <= cs; i++) {

                Node tmp =  q.remove();

                if (tmp.LP != null) {

                    q.add(tmp.LP);
                }
                if (tmp.RP != null) {

                    q.add(tmp.RP);
                }
            }
            h++;
        }
        System.out.println("Height of the tree : " + h);
    }

    public static int sum(Node R) {

        if (R == null) {

            return 0;
        }
        int ls = sum(R.LP);
        int rs = sum(R.RP);
        return (ls + rs + R.data);
    }

    public static int sumLLF(Node R) {
        if (R == null) return 0;

        int sum = 0;

        if (R.LP != null && R.LP.LP == null && R.LP.RP == null) {
            sum += R.LP.data;
        }

        sum += sumLLF(R.LP);
        sum += sumLLF(R.RP);

        return sum;
    }

    public static int sumRLF(Node R) {

        if (R == null) return 0;
        int sum = 0;
        if (R.RP != null && R.RP.LP == null && R.RP.RP == null) {
            sum += R.RP.data;
        }
        sum += sumRLF(R.LP);
        sum += sumRLF(R.RP);

        return sum;
    }

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);

        Node R = new Node(5);
        R.LP = new Node(12);
        R.LP.LP = new Node(4);
        R.LP.RP = new Node(8);
        R.LP.RP.LP = new Node(6);
        R.LP.RP.RP = new Node(9);
        R.RP =  new Node(10);
        R.RP.LP = new Node(2);
        R.RP.RP = new Node(15);
        R.RP.RP.LP = new Node(29);
        R.RP.RP.RP = new Node(20);
        R.RP.RP.LP.RP = new Node(40);

        System.out.println("1. Find Size of the Binary Tree \n2. Check if a given Node Value is present in the Binary Tree \n3. Return the Preorder Traversal of its Nodes' Values \n4. Return the Inorder Traversal of its Nodes' Values \n5. Return the Postorder Traversal of its Nodes' Values \n6. Return the Level order Traversal of its Nodes' Values \n7. Return an integer denoting the Height of the tree \n8. Return the Sum of all Nodes of the Binary Tree \n9. Return an integer denoting the sum of Node Value of all Left Leaves in the Tree \n10. Return an integer denoting the sum of Node Value of all Right Leaves in the Tree");
        int cnt = 0;
        do {

            System.out.println("Enter command : ");
            String s = sc.next();

            if (s.startsWith("size")) {

                System.out.println("Size of the tree : " + size(R));
            }
            else if (s.startsWith("checkIf")) {

                int k = Integer.parseInt(s.substring(8, s.length() - 1));
                checkIf(R, k);
            }
            else if (s.startsWith("preOrder")) {

                PrTT(R);
            }
            else if (s.startsWith("inOrder")) {

                ITT(R);
            } else if (s.startsWith("postOrder")) {

                PsTT(R);
            }
            else if (s.startsWith("levelOrder")) {

                levelOrder(R);
            }
            else if (s.startsWith("height")) {

                height(R);
            }
            else if (s.equals("sum")) {

                System.out.println("Sum of all nodes : " + sum(R));
            }
            else if (s.equals("sumLLF")) {

                System.out.println("Sum of left leaves : " + sumLLF(R));
            }
            else if (s.equals("sumRLF")) {

                System.out.println("Sum of right leaves : " + sumRLF(R));
            }
            else {

                System.out.println("Enter definite command");
            }

            System.out.println();
            System.out.println("Do you wish to continue? 0 - continue 1 - stop");
            cnt = sc.nextInt();
        } while (cnt == 0);
    }
}
*/

/*

// Lowest common ancestor
import java.lang.*;
import java.util.*;

public class Node {

    Node next;
    int data;
    Node LP, RP;

    Node(int x) {

        data = x;
        LP = null;
        RP = null;
    }
    public static Node find(Node R, int a, int b) {

        if (R == null) {

            return null;
        }
        if (R.data == a || R.data == b) {

            return R;
        }

        Node lfind = find(R.LP, a, b);
        Node rfind = find(R.RP, a, b);

        if (lfind != null && rfind != null) {

            return R;
        }

        return (lfind != null) ?lfind : rfind;
    }

    public static void main (String[] args) {

        Node R = new Node(7);
        R.LP = new Node(8);
        R.LP.LP = new Node(10);
        R.LP.LP.LP = new Node(41);
        R.LP.RP = new Node(11);
        R.LP.RP.LP = new Node(18);
        R.LP.RP.LP.LP = new Node(19);
        R.LP.RP.LP.LP.LP = new Node(21);
        R.LP.RP.LP.LP.RP = new Node(20);
        R.LP.RP.LP.LP.LP.LP = new Node(23);
        R.LP.RP.LP.LP.LP.RP = new Node(22);
        R.RP = new Node(9);
        R.RP.LP = new Node(12);
        R.RP.RP = new Node(13);
        R.RP.RP.LP = new Node(14);
        R.RP.RP.LP.RP = new Node(15);
        R.RP.RP.LP.RP.LP = new Node(16);
        R.RP.RP.LP.RP.LP.RP = new Node(17);

        int a = 22, b = 23;
        System.out.println("Lowest common ancestor : " + find(R, a, b).data);
    }
}
*/

/*

// Check if and level order
import java.lang.*;
import java.util.*;

public class Node {

    Node next;
    int data;
    Node LP, RP;

    Node (int x) {

        data = x;
        LP = null;
        RP = null;
    }

    public static void checkIf(Node R, int k) {

        Node T = R;
        int c = 0;
        while (T != null) {

            if (T.data == k) {

                System.out.println("Found");
                c++;
                break;
            }
            else if (T.data > k) {

                T = T.LP;
            }
            else {

                T = T.RP;
            }
        }
        if (c == 0) {

            System.out.println("Not found");
        }
    }

    public static Node insert (Node R, int k) {

        if (R == null) {

            Node x = new Node(k);
            return x;
        }
        else if (R.data > k) {

            R.LP = insert(R.LP, k);
        }
        else {

            R.RP = insert(R.RP, k);
        }

        return R;
    }

    public static void levelOrder (Node R) {

        Queue<Node> q = new LinkedList<>();
        q.add(R);
        while (q.size() > 0) {

            int cs = q.size();
            for (int i = 1; i <= cs; i++) {

                Node tmp =  q.remove();
                System.out.print(tmp.data + " ");

                if (tmp.LP != null) {

                    q.add(tmp.LP);
                }
                if (tmp.RP != null) {

                    q.add(tmp.RP);
                }
            }
            System.out.println();
        }
    }

    public static void main (String[] args) {

        Node R = new Node(25);
        R.LP = new Node(20);
        R.RP = new Node(35);
        R.LP.LP = new Node(10);
        R.LP.RP = new Node(24);
        R.LP.LP.RP = new Node(15);
        R.LP.RP.LP = new Node(23);
        R.RP.LP = new Node(34);
        R.RP.RP = new Node(40);
        R.RP.LP.LP = new Node(32);
        R.RP.RP.LP = new Node(37);
        R.RP.RP.RP = new Node(50);

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter value to check : ");
        int k = sc.nextInt();

        checkIf(R, k);

        System.out.println("Enter value to insert in the tree : ");
        int l = sc.nextInt();

        insert(R, l);

        levelOrder(R);
    }
}
 */

/*
// Level Order Printing
import java.lang.*;
import java.util.*;

public class Node {

    Node next;
    int data;
    Node LP, RP;

    Node(int x) {
        data = x;
        LP = null;
        RP = null;
    }

    public static void levelOrder (Node R) {

        Queue<Node> q = new LinkedList<>();
        q.add(R);
        while (q.size() > 0) {

            int cs = q.size();
            for (int i = 1; i <= cs; i++) {

                Node tmp =  q.remove();
                System.out.print(tmp.data + " ");

                if (tmp.LP != null) {

                    q.add(tmp.LP);
                }
                if (tmp.RP != null) {

                    q.add(tmp.RP);
                }
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        Node R = new Node(1);
        R.LP = new Node(2);
        R.LP.LP = new Node(4);
        R.LP.RP = new Node(5);
        R.LP.RP.RP = new Node(9);
        R.LP.RP.RP.LP = new Node(10);
        R.RP = new Node(3);
        R.RP.LP = new Node(6);
        R.RP.LP.LP = new Node(8);
        R.RP.RP = new Node(7);
        R.RP.RP.RP = new Node(11);
        R.RP.RP.LP = new Node(8);

        levelOrder(R);
    }
}
*/

/*
// Sum of leaf nodes
import java.lang.*;
import java.util.*;

public class Node {

    Node next;
    int data;
    Node LP, RP;

    Node(int x) {
        data = x;
        LP = null;
        RP = null;
    }

    public static int sumLLF(Node R) {
        if (R == null) return 0;

        int sum = 0;

        if (R.LP != null && R.LP.LP == null && R.LP.RP == null) {
            sum += R.LP.data;
        }

        sum += sumLLF(R.LP);
        sum += sumLLF(R.RP);

        return sum;
    }

    public static int sumRLF(Node R) {

        if (R == null) return 0;
        int sum = 0;
        if (R.RP != null && R.RP.LP == null && R.RP.RP == null) {
            sum += R.RP.data;
        }
        sum += sumRLF(R.LP);
        sum += sumRLF(R.RP);

        return sum;
    }

    public static void main(String[] args) {
        Node R = new Node(1);
        R.LP = new Node(2);
        R.LP.LP = new Node(4);
        R.LP.RP = new Node(5);
        R.LP.RP.RP = new Node(9);
        R.LP.RP.RP.LP = new Node(10);
        R.RP = new Node(3);
        R.RP.LP = new Node(6);
        R.RP.LP.LP = new Node(8);
        R.RP.RP = new Node(7);
        R.RP.RP.RP = new Node(11);
        R.RP.RP.LP = new Node(8);

        System.out.println("Sum of left leaf nodes is : " + sumLLF(R));
        System.out.println("Sum of right leaf nodes is : " + sumRLF(R));
    }
}
*/

/*
// Pre, in, post order
import java.lang.*;
import java.util.*;

public class Node {

    public Node next;
    int data;
    Node LP, RP;
    Node (int x) {

        data = x;
        LP = null;
        RP = null;
    }

    public static void PrTT (Node R) {

        if (R == null) {
            return;
        }
        System.out.print(R.data + " ");
        PrTT(R.LP);
        PrTT(R.RP);
    }

    public static void ITT (Node R) {

        if (R ==  null) {
            return;
        }
        ITT(R.LP);
        System.out.print(R.data + " ");
        ITT(R.RP);
    }

    public static void PsTT (Node R){

        if (R == null) {
            return;
        }
        PsTT(R.LP);
        PsTT(R.RP);
        System.out.print(R.data + " ");
    }

    public static int size(Node R) {

        if (R == null) {

            return 0;
        }
        int l = size(R.LP);
        int r = size(R.RP);
        return (l + r + 1);
    }

    public static int sum(Node R) {

        if (R == null) {

            return 0;
        }
        int ls = sum(R.LP);
        int rs = sum(R.RP);
        return (ls + rs + R.data);
    }

    public static void main (String[] args) {

        Node R = new Node(1);
        R.LP = new Node(2);
        R.LP.LP = new Node(4);
        R.LP.LP.RP = new Node(5);
        R.LP.RP = new Node(3);
        R.RP = new Node(6);
        R.RP.RP = new Node(7);
        R.RP.RP.LP = new Node(8);

        System.out.println("PreOrder : ");
        PrTT(R);
        System.out.println(" ");
        System.out.println("InOrder : ");
        ITT(R);
        System.out.println(" ");
        System.out.println("PostOrder : ");
        PsTT(R);
        System.out.println(" ");
        System.out.println("Size : " + size(R));
        System.out.println("Sum of elements : " + sum(R));
    }
}
*/

/*
// Creation of tree
import java.lang.*;
import java.util.*;

public class Node {

    public Node next;
    int data;
    Node LP, RP;
    Node (int x) {

        data = x;
        LP = null;
        RP = null;
    }

    public static void main (String[] args) {

        Node R = new Node(7);
        R.LP = new Node(6);
        R.RP = new Node(5);
        R.LP.LP = new Node(4);
        R.LP.LP.RP = new Node(3);

        System.out.println("Root node : " + R.data);
        System.out.println("Node to the left of root node : " + R.LP.data);
        System.out.println("Node to the right of root node : " + R.RP.data);
        System.out.println("Node to the left of left node of the root node : " + R.LP.LP.data);
        System.out.println("Node to the left of left of right node of the root node : " + R.LP.LP.RP.data);
    }
}
*/

/*
import java.lang.*;
import java.util.*;

public class Node {

    static Node H;
    static Node T = H;
    static int N;
    int data;
    Node next;
    Node (int x) {

        data = x;
        next = null;
    }

    public static void print() {

        System.out.print("Elements are : ");
        T = H;
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

    public static void deleteNode (int p) {

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

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);

        // getting size of linked list
        System.out.println("Enter size of linked list : ");
        int N = sc.nextInt();

        // getting linked list elements
        System.out.println("Enter elements of linked list : ");
        H = new Node(sc.nextInt());
        T = H;
        for (int i = 1; i < N; i++) {

            T.next = new Node(sc.nextInt());
            T = T.next;
        }

        // displaying elements
        print();

        // deleting an element
        System.out.println("Enter position to delete element : ");
        int p = sc.nextInt();
        deleteNode(p);
        print();
    }
}
*/

/*
public class Node {

    static Node H;
    static Node T = H;
    static int N;
    int data;
    Node next;
    Node (int x) {

        data = x;
        next = null;
    }

    public static void print() {

        System.out.print("Elements are : ");
        T = H;
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

    public static void reverse (Node T) {

        if (T == null) return;
        reverse(T.next);
        System.out.print(T.data + " -> ");
    }

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);

        // getting size of linked list
        System.out.println("Enter size of linked list : ");
        int N = sc.nextInt();

        // getting linked list elements
        System.out.println("Enter elements of linked list : ");
        H = new Node(sc.nextInt());
        T = H;
        for (int i = 1; i < N; i++) {

            T.next = new Node(sc.nextInt());
            T = T.next;
        }

        // displaying elements
        print();

        // getting reverse
        System.out.println("Reverse : ");
        T = H;
        reverse(T);

    }
}
*/

/*
public class Node {

    int data;
    Node next;
    Node (int x) {

        data = x;
        next = null;
    }

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);

        // getting size of linked list
        System.out.println("Enter size of linked list : ");
        int N = sc.nextInt();

        // getting linked list elements
        System.out.println("Enter elements of linked list : ");
        Node H = new Node(sc.nextInt());
        Node T = H;
        for (int i = 1; i < N; i++) {

            T.next = new Node(sc.nextInt());
            T = T.next;
        }

        // displaying linked list elements
        System.out.print("Elements are : ");
        T = H;
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

        // new node insertion
        System.out.println("Enter the position for insertion : ");
        int p = sc.nextInt();
        System.out.println("Enter the value of element : ");
        int v = sc.nextInt();

        if (p == 0) {

            Node Z = new Node(v);
            Z.next = H;
            H = Z;
        }

        else {

            Node X = H;
            for (int i = 0; i < p - 1; i++) {

                X = X.next;
            }
            Node Y = X.next;
            Node Z = new Node(v);
            X.next = Z;
            Z.next = Y;
        }
        System.out.print("Elements after insertion : ");
        T = H;
        count = 0;
        while (T != null) {

            count++;
            if (count == N + 1) {

                System.out.print(T.data);
            }
            else {

                System.out.print(T.data + " -> ");
            }
            T = T.next;
        }
    }
}
*/

/*
public class Node {

    int data;
    Node next;
    Node (int x) {
        data = x;
        next = null;
    }

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);
        // getting size of linked list
        System.out.println("Enter size of linked list : ");
        int N = sc.nextInt();

        // getting linked list elements
        System.out.println("Enter elements of linked list : ");
        Node H = new Node(sc.nextInt());
        Node T = H;
        for (int i = 1; i < N; i++) {

            T.next = new Node(sc.nextInt());
            T = T.next;
        }

        // displaying linked list elements
        System.out.print("Elements are : ");
        T = H;
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

        // new node insertion
        System.out.println("Enter the position for insertion : ");
        int p = sc.nextInt();
        System.out.println("Enter the value of element : ");
        int v = sc.nextInt();

        if (p == 0) {

            Node Z = new Node(v);
            Z.next = H;
            H = Z;
        }
        else {

            Node X = H;
            for (int i = 0; i < p - 1; i++) {

                X = X.next;
            }
            Node Y = X.next;
            Node Z = new Node(v);
            X.next = Z;
            Z.next = Y;
        }
        System.out.print("Elements after insertion : ");
        T = H;
        count = 0;
        while (T != null) {

            count++;
            if (count == N + 1) {

                System.out.print(T.data);
            }
            else {

                System.out.print(T.data + " -> ");
            }
            T = T.next;
        }
    }
}
*/

/*
public class Node {

    int data;
    Node next;

    Node (int x) {

        data = x;
        next = null;
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        // accepting size of linked list
        System.out.println("Enter the number of nodes : ");
        int N = sc.nextInt();

        // accepting elements of linked list
        System.out.println("Enter elements : ");
        Node H = new Node(sc.nextInt());
        Node T = H;
        for (int i = 1; i < N; i++) {

            T.next = new Node(sc.nextInt());
            T = T.next;
        }

        // printing elements of linked list
        System.out.print("Elements of the linked list are : ");
        int count = 0;
        T = H;
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

        // calculating size of linked list
        count = 0;
        T = H;
        while (T != null) {

            count++;
            T = T.next;
        }
        System.out.println(" ");
        System.out.println("The size of the linked list is : " + count);

        // finding kth element in the linked list
        System.out.println("Enter the value for k : ");
        int k = sc.nextInt();
        count = 0;
        T = H;
        while (T != null) {

            count++;
            if (count == k) {

                System.out.println("Element at kth position is : " + T.data);
            }
            T = T.next;
        }

        // searching an element in the linked list
        System.out.println("Enter element to be searched : ");
        int key = sc.nextInt();
        int f = 0;
        count = 0;
        T = H;
        while (T != null) {

            count ++;
            if(T.data == key) {
                System.out.println("Element found at " + count + " position");
                f++;
            }
            T = T.next;
        }
        if (f == 0) {

            System.out.println("Element not found");
        }
    }
}
*/
