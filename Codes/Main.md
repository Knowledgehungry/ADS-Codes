```java
/*
// Infix to Postfix

import java.lang.*;
import java.util.*;
class Stack {

    int N;
    char[] st;
    int sp;

    Stack(int x) {

        N = x;
        st = new char[N];
        sp = -1;
    }

    void push (char x) {

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

        if (sp == N - 1) return '\0';
        return st[sp];
    }
}

public class Main {

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.println("Enter string : ");
        String a = sc.next();
        Stack st = new Stack(a.length());

        for (int j = 0; j < a.length(); j++) {
            char c = a.charAt(j);

            if ((c >= 'a' && c <= 'z') || (c >= 'A' && c <= 'Z') || (c >= '0' && c <= '9')) {
                System.out.print(c);
            }
            else if (c == '(') {
                st.push(c);
            }
            else if (c == ')') {
                while (!st.isEmpty() && st.peek() != '(') {
                    System.out.print(st.pop());
                }
                if (!st.isEmpty()) {
                    st.pop();
                }
            }
            else {
                while (!st.isEmpty() && st.peek() != '(') {
                    char top = st.peek();
                    if ((top == '*' || top == '/') || ((top == '+' || top == '-') && (c == '+' || c == '-'))) {
                        System.out.print(st.pop());
                    } else {
                        break;
                    }
                }
                st.push(c);
            }
        }

        while (!st.isEmpty()) {

            System.out.print(st.pop());
        }
    }
}
*/

/*

// Terminal Commands

import java.lang.*;
import java.util.*;
class Stack {

    int N;
    char[] st;
    int sp;

    Stack(int x) {

        N = x;
        st = new char[N];
        sp = -1;
    }

    void print() {

        for (int i = 0; i <= sp; i++) {

            System.out.print(st[i] + " ");
        }
        System.out.println(" ");
    }

    void push (char x) {

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

        if (sp == N - 1) return '\0';
        return st[sp];
    }
}

public class Main {

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter size of string : ");
        int N = sc.nextInt();

        Stack st = new Stack(N);

        int c;
        do {

            System.out.println("Enter command : ");
            String s = sc.next();

            if (s.equals("st.push()")) {

                System.out.println("Enter : ");
                String num = sc.next();
                st.push(num.charAt(0));
            }
            else if (s.equals("st.pop()")) {

                System.out.println("Popped : " + st.pop());
            }
            else if (s.equals("st.peek()")) {

                System.out.println("Top : " + st.peek());
            }
            else {

                st.print();
            }

            System.out.println("Do you wish to continue? 0 - continue 1 - stop");
            c = sc.nextInt();
        } while (c == 0);
    }
}
*/

/*

// Remove consecutive characters

import java.lang.*;

class Stack {

    int N;
    char [] A = {'v', 's', 's', 'p', 'q', 'r', 'r', 'q', 'p', 'i', 't'};
    int sp;

    Stack() {

        N = A.length;
        sp = -1;
    }

    void push (char y) {

        if (sp == N - 1) {
            System.out.println("Stack is full");
        }
        else {
            A[++sp] = y;
        }
    }

    boolean isEmpty() {

        return sp == -1;
    }

    char pop() {

        if (isEmpty()) {

            System.out.println("Stack is empty");
            return 0;
        }
        return A[sp--];
    }

    char peek() {

        if (isEmpty()) return 0;
        return A[sp];
    }

    int size() {

        return sp + 1;
    }

    void result() {

        Stack st = new Stack();
        for (int i = 0; i < N; i++) {

            if (!st.isEmpty() && st.peek() == A[i]) {

                st.pop();
            }
            else {

                st.push(A[i]);
            }
        }

        System.out.println("Characters after removing consecutive same characters : ");
        char [] R = new char[st.size()];
        int j = 0;

        while (!st.isEmpty()) {

            R[j++] = st.pop();
        }

        for (int i = R.length - 1; i >= 0; i--) {

            System.out.print(R[i] + " ");
        }
    }
}

public class Main {

    public static void main (String[] args) {

        Stack s = new Stack();
        s.result();
    }
}
*/

/*

// Stack using Array

import java.lang.*;
import java.util.*;

class Stack {

    int N;
    int [] A;
    int sp;

    Stack(int x) {

        N = x;
        A = new int[N];
        sp = -1;
    }

    void print() {

        for (int i = 0; i < N; i++) {

            System.out.print(A[i] + " ");
        }
    }

    void push (int y) {

        if (sp == N - 1) {

            System.out.println("Stack is full");
        }
        A[++sp] = y;
    }

    boolean isEmpty() {

        return sp == -1;
    }

    int pop() {

        if (isEmpty()) {

            System.out.println("Stack is empty");
        }
        int el = A[sp--];
        return el;
    }

    int peek() {

        if (sp == N - 1) return -1;
        return A[sp];
    }

    int size() {

        return sp + 1;
    }

}

public class Main {

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter size : ");
        int N = sc.nextInt();
        Stack s = new Stack(N);
        System.out.println("Enter elements : ");
        for (int i = 0; i < N; i++) {

            s.push(sc.nextInt());
        }
        System.out.println("Elements after push : ");
        s.print();

        System.out.println(" ");
        System.out.println("Element popped : " + s.pop());

        System.out.println("Element at the top : " + s.peek());

        System.out.println("Size : " + s.size());

        System.out.println("Stack is empty? - " + s.isEmpty());
    }
}
*/


/*
// Stack using LinkedList

import java.lang.*;
import java.util.*;

class Stack1 {

    Node H;
    int cnt;

    Stack1() {

        H = null;
        cnt = 0;
    }

    void print() {

        Node T = H;
        while (T != null) {

            System.out.print(T.data + " -> ");
            T = T.next;
        }
        System.out.println(" ");
    }

    void push(int x) {

        if (H == null) {

            H = new Node(x);
        }
        else {

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

        return (H == null);
    }

}

public class Main {

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);
        Stack1 s = new Stack1();
        System.out.println("Enter size : ");
        int N = sc.nextInt();
        System.out.println("Enter elements : ");
        for (int i = 0; i < N; i++) {

            s.push(sc.nextInt());
        }
        System.out.println("Elements after push : ");
        s.print();

        System.out.println("Element popped : " + s.pop());

        System.out.println("Element at the top : " + s.peek());

        System.out.println("Size : " + s.size());

        System.out.println("Stack is empty?" + s.isEmpty());
    }
}
*/
