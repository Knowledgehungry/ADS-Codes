# Binary Search Code

```java
import java.lang.*;
import java.util.*;

public class BinarySearch {

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);

        int c;
        do {

            System.out.println("1. Linear Search \n2. Binary Search \nEnter your choice : ");
            int ch = sc.nextInt(); // accepting choice
            switch (ch) { // passing 'ch' as a parameter to switch case

                case 1 : // Linear Search
                {
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
                            f++; // flag gets incremented
                        }
                    }

                    if(f == 0) { // if the 'f' does not get incremented then the following code will get executed
                        System.out.println(k + " not found in the array");
                    }
                    break;
                }

                case 2 : // Binary Search
                {
                    System.out.println("Enter size of array : ");
                    int size = sc.nextInt(); // accepting array size
                    int[] arr = new int[size];
                    System.out.println("Enter array elements : ");
                    for (int i = 0; i < size; i++) { // this loop will get executed until 'i' is less than 'size'

                        arr[i] = sc.nextInt(); // accepting array elements
                    }

                    Arrays.sort(arr); // sorting array
                    System.out.println("Enter element to be searched : ");
                    int key = sc.nextInt(); // accepting search element

                    int start = 0, end = size - 1, f = 0;
                    while (start <= end) { // this loop gets executed until 'start' is less than 'end'

                        int m = (start + end) / 2; // calculating middle value
                        if(arr[m] == key) { // if value at 'm' position in array matches 'key' the following code will get executed

                            System.out.println(key + " found at " + m + " position in the array");
                            f++; // flag gets incremented
                            break;
                        } else if (key < arr[m]) { // if 'key' is greater than value at 'm' position in array the following code will get executed

                            end = m - 1;
                        }
                        else {

                            start = m + 1;
                        }
                    }
                    if (f == 0) { // if the 'f' does not get incremented then the following code will get executed

                        System.out.println(key + " not found in the array");
                    }
                    break;
                }

                default:
                {
                    System.out.println("Please enter valid choice");
                    break;
                }
            }

            System.out.println("Do you wish to continue? Enter 0 - stop, 1 - continue : ");
            c = sc.nextInt();
        } while (c == 1); // the whole code wil get executed till value of 'c' is equal to 1
    }
}
