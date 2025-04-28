```java
import java.lang.*;
import java.util.*;

public class Searching {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter size of array : ");
        int size = sc.nextInt();
        int[] arr = new int[size];
        System.out.println("Enter array elements : ");
        for (int i = 0; i < size; i++) {

            arr[i] = sc.nextInt();
        }
        System.out.println("Enter element to find : ");
        int key = sc.nextInt();
        int start = 0, end = size - 1;
        while (start <= end) {

            int mid = (start + end) / 2;
            if (arr[mid] == key) {

                System.out.println("Element found at : " + mid);
            }

            if (key <= arr[mid]) {

                if (arr[start] <= key && key < arr[mid]) {

                    end = mid - 1;
                }
                else {

                    start = mid + 1;
                }
            }
            else {

                if (arr[mid] < key && key <= arr[end]) {

                    start = mid + 1;
                }
                else {

                    end = mid - 1;
                }
            }
        }
    }
}
