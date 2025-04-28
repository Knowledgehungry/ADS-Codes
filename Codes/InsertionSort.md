# Insertion Sort Code

```java
import java.lang.*;
import java.util.*;

public class InsertionSort {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter size of array : ");
        int size = sc.nextInt();
        int [] arr = new int[size];
        System.out.println("Enter array elements : ");
        for (int i = 0; i < size; i++) {

            arr[i] = sc.nextInt();
        }

        int comp = 0;
        int swaps = 0;
        for (int i = 1; i < size; i++) {

            int temp = arr[i];
            int j = i - 1;
            while (j >= 0) {

                comp++;
                if (arr[j] > temp) {

                    arr[j + 1] = arr[j];
                    j--;
                    swaps++;
                }
            }
            arr[j + 1] = temp;
        }

        System.out.println("No. of comparisons : " + comp);
        System.out.println("No. of swaps : " + swaps);
        System.out.println("Sorted array : ");
        for (int i = 0; i < size; i++) {

            System.out.print(arr[i] + " ");
        }
    }
}
