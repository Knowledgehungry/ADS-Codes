```java
/*
import java.lang.*;
import java.util.*;

public class Main1 {

    public static void main(String[] args) {

        ArrayList<Integer> a = new ArrayList<>();
        ArrayList<Integer> b = new ArrayList<>();
        ArrayList<Integer> c = new ArrayList<>();
        ArrayList<ArrayList<Integer>> ans = new ArrayList<>();
        a.add(1);
        b.add(1);
        b.add(2);
        c.add(1);
        c.add(2);
        c.add(3);
        ans.add(a);
        ans.add(b);
        ans.add(c);

        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
        System.out.println(ans);
        System.out.println(ans.get(0).get(0));
        System.out.println(ans.get(1).get(0));
    }
}
*/

/*
// Queue using stack

import java.util.Stack;

public class Main1 {

    Stack<Integer> st1 = new Stack<>();
    Stack<Integer> st2 = new Stack<>();

    public void enqueue(int x) {
        st1.push(x);
    }

    public int dequeue() {

        if (st2.isEmpty()) {

            if (st1.isEmpty()) {

                System.out.println("Empty");
            }
        }

        while (!st1.isEmpty()) {

            st2.push(st1.pop());
        }

        return st2.pop();
    }

    public int peek() {

        if (st2.isEmpty()) {

            if (st1.isEmpty()) {

                System.out.println("Empty");
            }

            while (!st1.isEmpty()) {

                st2.push(st1.pop());
            }
        }
        return st2.peek();
    }

    public int size() {

        return st1.size() + st2.size();
    }

    boolean isEmpty() {

        return st1.isEmpty() && st2.isEmpty();
    }

    public void print() {

        System.out.println("Stack 1 : " + st1);
        System.out.println("Stack 2 : " + st2);
    }

    public static void main (String[] args) {

        Main1 QS = new Main1();
        QS.enqueue(1);
        QS.enqueue(2);
        QS.enqueue(3);

        System.out.println("Dequeue element : " + QS.dequeue());
        System.out.println("Front element : " + QS.peek());
        System.out.println("Size : " + QS.size());
        System.out.println("Is queue empty : " + QS.isEmpty());
        QS.print();
    }
}
*/

/*
// Arraylist
import java.lang.*;
import java.util.*;
import java.util.LinkedList;

class Main1 {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter size : ");
        int N = sc.nextInt();
        Queue<Integer> Q = new LinkedList<>();
        ArrayList<Integer> ans = new ArrayList<>();
        Q.add(1);
        Q.add(2);
        Q.add(3);
        int cnt = 3;
        while (ans.size() < N) {

            int tmp = Q.remove();
            ans.add(tmp);
            if (cnt < N) {

                int n1 = tmp * 10 + 1;
                int n2 = tmp * 10 + 2;
                int n3 = tmp * 10 + 3;
                Q.add(n1);
                Q.add(n2);
                Q.add(n3);

                cnt = cnt + 3;
            }
         }
        System.out.println(ans);
    }
}
*/

/*
// Queue using linkedlist

import java.lang.*;
import java.util.*;

class Queue {

    Node H, T;
    int cnt;
    Queue () {

        H = T = null;
        cnt = 0;
    }

    void print() {

        Node X = H;
        while (X != null) {
            System.out.print(X.data + " ");
            X = X.next;
        }
        System.out.println(" ");
    }

    boolean isEmpty() {

        return H == null;
    }

    void enqueue (int x) {

        Node Y = new Node(x);
        if (T == null) {

            H = T = Y;
        }
        else {

            T.next = Y;
            T = T.next;
        }
        cnt++;
    }

    int dequeue() {

        if (isEmpty()) {

            return -1;
        }
        int el = H.data;
        H = H.next;
        if (H == null) {

            T = null;
        }
        cnt--;
        return el;
    }

    int front() {

        return H.data;
    }

    int rear() {

        return T.data;
    }

    int size() {
        return cnt;
    }
}

public class Main1 {

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);
        Queue q = new Queue();

        System.out.println("Enter size : ");
        int N = sc.nextInt();

        System.out.println("Enter elements : ");
        for (int i = 0; i < N; i++) {
            q.enqueue(sc.nextInt());
        }

        System.out.println("Enter element to insert : ");
        int num = sc.nextInt();
        q.enqueue(num);
        q.print();

        System.out.println("Element pushed out queue : " + q.dequeue());
        System.out.println("Element in the front : " + q.front());
        System.out.println("Element in the rear : " + q.rear());
        System.out.println("Size : " + q.size());
    }
}
*/

/*
// Queue using array

import java.lang.*;
import java.util.*;

class Queue {

    int N;
    int[] A;
    int F, R;
    int cnt;

    Queue (int x) {

        N = x;
        A = new int[x];
        F = 0;
        R = 0;
        cnt = 0;
    }

    boolean isEmpty() {

        return (cnt == 0);
    }

    boolean isFull() {

        return cnt == N;
    }
    
    void enqueue (int y) {

        if (isFull()) {
            System.out.println("Full");
        }
        A[R] = y;
        R++;
        cnt++;
    }

    int dequeue() {

        if (isEmpty()) {
            System.out.println("Empty");
        }
        int el = A[F];
        F++;
        cnt--;
        return el;
    }

    int front() {

        if (isEmpty()) return -1;
        return A[F];
    }

    int rear() {

        if (isEmpty()) return -1;
        return A[R - 1];
    }

    int size() {
        return cnt;
    }
}

public class Main1 {

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.println("Enter size : ");
        int N = sc.nextInt();

        Queue q = new Queue(N);
        System.out.println("Enter elements : ");
        for (int i = 0; i < N; i++) {
            q.enqueue(sc.nextInt());
        }

        System.out.println("Size : " + q.size());
        System.out.println("Element in the front : " + q.front());
        System.out.println("Element in the rear : " + q.rear());
        System.out.println("Element pushed out queue : " + q.dequeue());
        System.out.println("Size : " + q.size());
        System.out.println("Element in the front : " + q.front());
    }
}
*/
