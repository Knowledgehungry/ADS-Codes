```java
/*
import java.lang.*;
import java.util.*;

class QueueList {

    Node H, T;
    int cnt;
    QueueList () {

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

class QueueArray {

    int N;
    int[] A;
    int F, R;
    int cnt;

    QueueArray (int x) {

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

    void print() {

        for (int i = 0; i < N; i++) {

            System.out.print(A[i] + " ");
        }
        System.out.println(" ");
    }

    void enqueue (int y) {

        if (isFull()) {

            System.out.println("Queue is full");
        }
        A[R] = y;
        R++;
        cnt++;
    }

    int dequeue() {

        if (isEmpty()) {

            System.out.println("Queue is empty");
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

class QueueStack {

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
}

public class QueueMain {

    public static void cmd(String s, QueueList queueList) {

        if (s.startsWith("q.enqueue")) {

            int x = Integer.parseInt(s.substring(10, s.length() - 1));
            queueList.enqueue(x);
            queueList.print();
        }
        else if (s.startsWith("q.dequeue")) {

            System.out.println("Element dequeued : " + queueList.dequeue());
            queueList.print();
        }
        else if (s.startsWith("q.front")) {

            System.out.println("Element at front : " + queueList.front());
        }
        else if (s.startsWith("q.rear")) {

            System.out.println("Element at rear : " + queueList.rear());
        }
        else if (s.startsWith("q.isEmpty")) {

            System.out.println("Is it empty? - " + queueList.isEmpty());
        }
        else if (s.startsWith("q.size")) {

            System.out.println("Size : " + queueList.size());
        }
        else {

            System.out.println("Enter valid command!");
        }
    }

    public static void cmd(String s, QueueArray queueArray) {

        if (s.startsWith("q.enqueue")) {

            int x = Integer.parseInt(s.substring(10, s.length() - 1));
            queueArray.enqueue(x);
            queueArray.print();
        }
        else if (s.startsWith("q.dequeue")) {

            System.out.println("Element dequeued : " + queueArray.dequeue());
            queueArray.print();
        }
        else if (s.startsWith("q.front")) {

            System.out.println("Element at front : " + queueArray.front());
        }
        else if (s.startsWith("q.rear")) {

            System.out.println("Element at rear : " + queueArray.rear());
        }
        else if (s.startsWith("q.isEmpty")) {

            System.out.println("Is it empty? - " + queueArray.isEmpty());
        }
        else if (s.startsWith("q.size")) {

            System.out.println("Size : " + queueArray.size());
        }
        else {

            System.out.println("Enter valid command!");
        }
    }

    public static void cmd(String s, QueueStack queueStack) {

        if (s.startsWith("q.enqueue")) {

            int x = Integer.parseInt(s.substring(10, s.length() - 1));
            queueStack.enqueue(x);
            queueStack.print();
        }
        else if (s.startsWith("q.dequeue")) {

            System.out.println("Element dequeued : " + queueStack.dequeue());
            queueStack.print();
        }
        else if (s.startsWith("q.peek")) {

            System.out.println("Element at peek : " + queueStack.peek());
        }
        else if (s.startsWith("q.isEmpty")) {

            System.out.println("Is it empty? - " + queueStack.isEmpty());
        }
        else if (s.startsWith("q.size")) {

            System.out.println("Size : " + queueStack.size());
        }
        else {

            System.out.println("Enter valid command!");
        }
    }

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);

        int ct = 0;
        do {

            System.out.println("Enter option : \n 1. Queue using LinkedList \n 2. Queue using Array \n 3. Queue using Stack \n 4. Queue Number");
            int op = sc.nextInt();
            switch (op) {

                case 1 :
                {

                    QueueList q = new QueueList();
                    int c;
                    do {

                        System.out.println("Enter command : ");
                        String s = sc.next();
                        cmd(s, q);
                        System.out.println("Do you wish to continue? 0 - continue 1 - stop");
                        c = sc.nextInt();
                    } while (c == 0);
                    break;
                }

                case 2 :
                {

                    System.out.println("Enter size of array : ");
                    int N = sc.nextInt();
                    QueueArray q = new QueueArray(N);
                    int c;
                    do {

                        System.out.println("Enter command : ");
                        String s = sc.next();
                        cmd(s, q);
                        System.out.println("Do you wish to continue? 0 - continue 1 - stop");
                        c = sc.nextInt();
                    } while (c == 0);
                    break;
                }

                case 3 :
                {

                    QueueStack q = new QueueStack();
                    int c;
                    do {

                        System.out.println("Enter command : ");
                        String s = sc.next();
                        cmd(s, q);
                        System.out.println("Do you wish to continue? 0 - continue 1 - stop");
                        c = sc.nextInt();
                    } while (c == 0);
                    break;
                }

                case 4 :
                {

                    System.out.println("Enter size : ");
                    int N = sc.nextInt();
                    Queue<Integer> Q = new LinkedList<>();
                    ArrayList<Integer> ans = new ArrayList<>();
                    int c;
                    do {
                        System.out.println("Enter command : ");
                        String s = sc.next();
                        int count = 0;
                        if (s.startsWith("q.add")) {

                            int x = Integer.parseInt(s.substring(6, s.length() - 1));
                            Q.add(x);
                            count++;
                        }
                        else if (s.startsWith("q.display")) {

                            while (ans.size() < N) {

                                int tmp = Q.remove();
                                ans.add(tmp);
                                if (count < N) {

                                    int n1 = tmp * 10 + 1;
                                    int n2 = tmp * 10 + 2;
                                    int n3 = tmp * 10 + 3;
                                    Q.add(n1);
                                    Q.add(n2);
                                    Q.add(n3);

                                    count = count + 3;
                                }
                            }
                            System.out.println(ans);
                        }
                        System.out.println("Do you wish to continue? 0 - continue 1 - stop");
                        c = sc.nextInt();
                    } while (c == 0);

                    break;
                }

                default :
                {
                    System.out.println("Enter a valid option!");
                }
            }
            System.out.println("Do you wish to continue? 0 - continue 1 - stop");
            ct = sc.nextInt();
        } while (ct == 0);

    }
}
*/
