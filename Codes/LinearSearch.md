# Linear Search Code

```java
import java.lang.*;
import java.util.*;

class LinearSearch {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        int size;
        System.out.println("Enter size of array : ");
        size = sc.nextInt(); // accepting array size
        int[] A = new int[size];

        System.out.println("Enter elements of array : ");
        for(int i = 0; i < size; i++) { // this loop will get executed until 'i' is less than 'size'

            A[i] = sc.nextInt(); //accepting array elements
        }

        int f = 0;
        int k;
        System.out.println("Enter element to be searched : ");
        k = sc.nextInt(); // accepting search element

        for(int i = 0; i < size; i++){ // this loop will get executed until 'i' is less than 'size'

            if(A[i] == k) { // if the element at 'i' position in the array matches 'k' then the following code will get executed

                System.out.println(k + " found at " + i + " position in the array");
                f++; // 'flag' gets incremented
            }
        }

        if(f == 0) { // if the 'flag' does not get incremented then the following code will get executed
            System.out.println(k + " not found in the array");
        }
    }
}
