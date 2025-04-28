# Directed Weighted Graph

```java
import java.util.ArrayList;

class Pair {

    int y;
    int wt;

    Pair(int y, int wt) {

        this.y = y;
        this.wt = wt;
    }
}

public class DWGraph {

    public static void main (String[] args) {

        int V = 7;
        int E = 8;
        int[][] e = {{0, 3, 10}, {0, 1, 5}, {2, 3, 9}, {3, 4, 3}, {1, 2, 4},
                {4, 5, 7}, {4, 6, 10}, {5, 6, 15}};

        ArrayList<ArrayList<Pair>> graph = new ArrayList<>();

        for (int i = 0; i < V; i++) {

            graph.add(new ArrayList<>());
        }

        for (int i = 0; i < E; i++) {

            int x = e[i][0];
            int y = e[i][1];
            int wt = e[i][2];

            Pair p = new Pair(y, wt);
            graph.get(x).add(p);
        }

        for (int i = 0; i < V; i++) {

            ArrayList<Pair> list = graph.get(i);
            System.out.print(i + "-->");
            for (int nbr = 0; nbr < list.size(); nbr++) {

                Pair e1 = list.get(nbr);
                System.out.println("(" + e1.y + ", " + e1.wt + ")");
            }
            System.out.println();
        }
    }
}
