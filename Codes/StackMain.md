```java
import java.lang.*;
import java.util.*;

class Node {

    int data;
    Node next;

    Node(int x) {
        data = x;
        next = null;
    }
}

class StackList {
    Node H;
    int cnt;

    StackList() {
        H = null;
        cnt = 0;
    }

    void printList() {

        Node T = H;
        while (T != null) {

            System.out.print(T.data + " ");
            T = T.next;
        }
        System.out.println();
    }

    void push(int x) {

        if (H == null) {

            H = new Node(x);
        }
        else  {

            Node Y = new Node(x);
            Y.next = H;
            H = Y;
        }
        cnt++;
    }

    int pop() {

        if (H == null) return -1;
        int el = H.data;
        H = H.next;
        cnt--;
        return el;
    }

    int peek() {

        if (H == null) return -1;
        return H.data;
    }

    int size() {

        return cnt;
    }

    boolean isEmpty() {

        return H == null;
    }
}

class StackArray {

    int N;
    int[] A;
    int sp;

    StackArray(int x) {

        N = x;
        A = new int[N];
        sp = -1;
    }

    void printArray() {

        for (int i = 0; i <= sp; i++) {

            System.out.print(A[i] + " ");
        }
        System.out.println();
    }

    void push(int y) {

        if (sp == N - 1) {

            System.out.println("Stack is full");
            return;
        }
        A[++sp] = y;
    }

    boolean isEmpty() {

        return sp == -1;
    }

    int pop() {

        if (isEmpty()) {

            System.out.println("Stack is empty");
            return -1;
        }
        return A[sp--];
    }

    int peek() {

        if (isEmpty()) return -1;
        return A[sp];
    }

    int size() {

        return sp + 1;
    }
}

class StackFix {

    int N;
    char[] st;
    int sp;

    StackFix(int x) {

        N = x;
        st = new char[N];
        sp = -1;
    }

    void push(char x) {

        if (sp == N - 1) {

            System.out.println("Stack is full");
            return;
        }
        st[++sp] = x;
    }

    boolean isEmpty() {

        return sp == -1;
    }

    char pop() {

        if (isEmpty()) {

            System.out.println("Stack is empty");
            return '\0';
        }
        return st[sp--];
    }

    char peek() {

        if (isEmpty()) return '\0';
        return st[sp];
    }
}

public class StackMain {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("\n1. Stack using LinkedList \n2. Stack using Array \n3. Infix to Postfix");
        int cnt;

        do {
            System.out.println("Enter option: ");
            int ch = sc.nextInt();
            sc.nextLine();

            switch (ch) {

                case 1: {
                    StackList st = new StackList();
                    int c;
                    do {
                        System.out.println("Enter command : ");
                        String s = sc.nextLine();

                        if (s.startsWith("st.push")) {

                            int x = Integer.parseInt(s.substring(8, s.length() - 1));
                            st.push(x);
                            System.out.println("Pushed");
                        }
                        else if (s.startsWith("st.pop")) {

                            System.out.println("Popped : " + st.pop());
                        }
                        else if (s.startsWith("st.peek")) {

                            System.out.println("Top : " + st.peek());
                        }
                        else if (s.startsWith("st.size")) {

                            System.out.println("Size : " + st.size());
                        }
                        else if (s.startsWith("st.isEmpty")) {

                            System.out.println("Stack is empty? - " + st.isEmpty());
                        }
                        else if (s.startsWith("st.printList")) {

                            st.printList();
                        }
                        else {

                            System.out.println("Enter valid command!");
                        }
                        System.out.println("Do you wish to continue? 0 - continue 1 - stop");
                        c = sc.nextInt();
                        sc.nextLine();
                    } while (c == 0);
                    break;
                }

                case 2: {
                    System.out.println("Enter size of stack: ");
                    int N = sc.nextInt();
                    sc.nextLine();
                    StackArray st = new StackArray(N);

                    int c;
                    do {
                        System.out.println("Enter command : ");
                        String s = sc.nextLine();

                        if (s.startsWith("st.push")) {

                            int x = Integer.parseInt(s.substring(8, s.length() - 1));
                            st.push(x);
                            System.out.println("Pushed");
                        }
                        else if (s.startsWith("st.pop")) {

                            System.out.println("Popped : " + st.pop());
                        }
                        else if (s.startsWith("st.peek")) {

                            System.out.println("Top : " + st.peek());
                        }
                        else if (s.startsWith("st.size")) {

                            System.out.println("Size : " + st.size());
                        }
                        else if (s.startsWith("st.isEmpty")) {

                            System.out.println("Stack is empty? - " + st.isEmpty());
                        }
                        else if (s.startsWith("st.printArray")) {

                            st.printArray();
                        }
                        else {

                            System.out.println("Enter valid command!");
                        }
                        System.out.println("Do you wish to continue? 0 - continue 1 - stop");
                        c = sc.nextInt();
                        sc.nextLine();
                    } while (c == 0);
                    break;
                }

                case 3: {
                    int b;
                    do {

                        System.out.println("Enter infix string : ");
                        String a = sc.nextLine();
                        StackFix st = new StackFix(a.length());

                        for (int j = 0; j < a.length(); j++) {
                            char c = a.charAt(j);
                            if (Character.isLetterOrDigit(c)) {

                                System.out.print(c);
                            }
                            else if (c == '(') {

                                st.push(c);
                            }
                            else if (c == ')') {

                                while (!st.isEmpty() && st.peek() != '(') {

                                    System.out.print(st.pop());
                                }

                                if (!st.isEmpty()) st.pop();
                            }
                            else {

                                while (!st.isEmpty() && precedence(st.peek()) >= precedence(c)) {

                                    System.out.print(st.pop());
                                }
                                st.push(c);
                            }
                        }
                        while (!st.isEmpty()) System.out.print(st.pop());

                        System.out.println();
                        System.out.println("Do you wish to continue? 0 - continue 1 - stop");
                        b = sc.nextInt();
                        sc.nextLine();
                    } while (b == 0);
                    break;
                }

                default:
                    System.out.println("Invalid option!");
            }

            System.out.print("Do you wish to continue? 0 - continue, 1 - stop: ");
            String cont = sc.nextLine();
            try {

                cnt = Integer.parseInt(cont);
            }
            catch (NumberFormatException e) {

                System.out.println("Invalid input. Exiting.");
                break;
            }

        } while (cnt == 0);
    }

    static int precedence(char op) {
        if (op == '+' || op == '-') return 1;
        if (op == '*' || op == '/') return 2;
        return 0;
    }
}

