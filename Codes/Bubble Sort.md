# Bubble Sort Code

```java
import java.lang.*;
import java.util.*;
public class BubbleSort {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter size of array : ");
        int size = sc.nextInt();
        int[] arr = new int[size];
        System.out.println("Enter array elements : ");
        for (int i = 0; i < size; i++) {

            arr[i] = sc.nextInt();
        }

        int count = 0;
        int swaps = 0;
        for (int i = 0; i < size - 1; i++) {

            int f = 0;
            for (int j = 0; j < size - i - 1; j++) {

                count++;
                if (arr[j] > arr[j + 1]) {

                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    f++;
                    swaps++;
                }
            }
            if (f == 0) {

                break;
            }
        }
        System.out.println("No. of comparisons : " + count);
        System.out.println("No. of swaps : " + swaps);
        System.out.println("Sorted array : ");
        for (int i = 0; i < size; i++) {

            System.out.print(arr[i] + " ");
        }
    }
}
