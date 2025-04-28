# Cycle Code

```java
import java.lang.*;

public class Cycle {

    int data;
    Node next;

    Cycle (int x) {
        data = x;
        next = null;
    }

    public static void main (String [] args) {

        Node H = new Node(1);
        Node b = new Node(2);
        Node c = new Node(3);
        Node d = new Node(4);
        Node e = new Node(5);

        H.next = b;
        b.next = c;
        c.next = d;
        d.next = e;
        e.next = c;

        Node S = H;
        Node F = H;
        int count = 0;

        while(F.next != null) {

            S = S.next;
            F = F.next.next;

            if (S == F) {
                System.out.println("Cycle");
                count++;
                break;
            }
        }
        if (count == 0) {
            System.out.println("Not cycle");
        }
    }
}
