# Creation of Undirected Graph Code

```java
import java.lang.*;

public class Graph {

    public static void main (String[] args) {

        int V = 7;
        int[][] E = {{0, 3}, {0, 1}, {2, 3}, {3, 4}, {1, 2}, {4, 5}, {4, 6}, {5, 6}};
        int[][] Graph = new int[V][V];
        for (int i = 0; i < E.length; i++) {

            int x = E[i][0];
            int y = E[i][1];
            Graph[x][y] = 1;
            Graph[y][x] = 1;
        }
        for (int i = 0; i < V; i++) {

            for (int j = 0; j < V; j++) {

                System.out.print(Graph[i][j] + " ");
            }
            System.out.println();
        }
    }
}

```

# Creation of Weighted Graph Code

```java
import java.lang.*;

public class Graph {

    public static void main (String[] args) {

        int V = 7;
        int[][] E = {{0, 3, 10}, {0, 1, 5}, {2, 3, 9}, {3, 4, 3}, {1, 2, 4}, {4, 5, 7}, {4, 6, 10}, {5, 6, 15}};
        int[][] Graph = new int[V][V];
        for (int i = 0; i < E.length; i++) {

            int x = E[i][0];
            int y = E[i][1];
            int wt = E[i][2];
            Graph[x][y] = wt;
        }
        for (int i = 0; i < V; i++) {

            for (int j = 0; j < V; j++) {

                System.out.print(Graph[i][j] + " ");
            }
            System.out.println();
        }
    }
}
