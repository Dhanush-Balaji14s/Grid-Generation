import java.util.*;

public class GridGeneration {

    private static final int[] EVENS = {2,4,6,8,10,12,14,16,18,20};

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int N = readInt(sc, "Enter array size (for NxN array): ", 1, 15);

        int[][] grid = generateGrid(N);

        System.out.println("\nGenerated 2D array:");
        printHeader(N);
        printGrid(grid, -1);

        int X = readInt(sc, "\nEnter a number to highlight (even number 2–20): ", 2, 20, true);

        System.out.println("\nStep 2:\n");
        System.out.println("Enter a number to highlight (even number 2–20): " + X);
        System.out.println("Array with " + X + " highlighted:");
        printHeader(N);
        int count = printGrid(grid, X);

        System.out.println("\nNumber " + X + " appeared " + count + " time(s)");
    }

    private static int readInt(Scanner sc, String msg, int min, int max) {
        return readInt(sc, msg, min, max, false);
    }

    private static int readInt(Scanner sc, String msg, int min, int max, boolean mustBeEven) {
        while (true) {
            System.out.print(msg);
            String input = sc.nextLine().trim();
            try {
                int val = Integer.parseInt(input);
                if (val < min || val > max) {
                    System.out.println("Invalid: Enter between " + min + " and " + max);
                    continue;
                }
                if (mustBeEven && val % 2 != 0) {
                    System.out.println("Invalid: Number must be EVEN.");
                    continue;
                }
                return val;
            } catch (Exception e) {
                System.out.println("Invalid input. Enter a number.");
            }
        }
    }

    private static int[][] generateGrid(int N) {
        Random r = new Random();
        int[][] arr = new int[N][N];
        for (int i = 0; i < N; i++)
            for (int j = 0; j < N; j++)
                arr[i][j] = EVENS[r.nextInt(EVENS.length)];
        return arr;
    }

    private static void printHeader(int N) {
        System.out.print("    ");
        for (int i = 0; i < N; i++)
            System.out.printf("%02d  ", i);
        System.out.println();
        printBorder(N);
    }

    private static void printBorder(int N) {
        System.out.print("   +");
        for (int i = 0; i < N; i++)
            System.out.print("---+");
        System.out.println();
    }

    private static int printGrid(int[][] grid, int highlight) {
        int count = 0;
        int N = grid.length;

        for (int i = 0; i < N; i++) {
            System.out.printf("%02d |", i);
            for (int j = 0; j < N; j++) {
                int val = grid[i][j];
                if (val == highlight) {
                    System.out.printf("[%2d]|", val);
                    count++;
                } else {
                    System.out.printf(" %2d |", val);
                }
            }
            System.out.println();
            printBorder(N);
        }
        return count;
    }
}
