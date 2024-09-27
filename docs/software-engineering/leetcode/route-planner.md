## C#

```c#
using System;
using System.Collections.Generic;

public class RoutePlanner
{
    static Dictionary<Tuple<int, int>, bool> visited = new Dictionary<Tuple<int, int>, bool>();

    private static bool isValidPosition(int row, int column, bool[,] mapMatrix)
    {
        if (row < 0 || column < 0)
        {
            return false;
        }

        if (row >= mapMatrix.GetLength(0) || column >= mapMatrix.GetLength(1))
        {
            return false;
        }

        return true;
    }

    public static bool RouteExists(int fromRow, int fromColumn, int toRow, int toColumn,
                                      bool[,] mapMatrix)
    {
        // check if valid position
        if (!isValidPosition(fromRow, fromColumn, mapMatrix))
        {
            return false;
        }

        // check if already visited
        if (visited.ContainsKey(Tuple.Create(fromRow, fromColumn)))
        {
            return false;
        }

        visited.Add(Tuple.Create(fromRow, fromColumn), true);

        // if not road
        if (mapMatrix[fromRow, fromColumn] == false)
        {
            return false;
        }

        // if found the end
        if (fromRow == toRow && fromColumn == toColumn)
        {
            return true;
        }

        // check up
        bool up = RouteExists(fromRow - 1, fromColumn, toRow, toColumn, mapMatrix);

        if (up) {
            return true;
        }

        // check down
        bool down = RouteExists(fromRow + 1, fromColumn, toRow, toColumn, mapMatrix);

        if (down) {
            return true;
        }

        // check left
        bool left = RouteExists(fromRow, fromColumn - 1, toRow, toColumn, mapMatrix);

        if (left) {
            return true;
        }

        // check right
        bool right = RouteExists(fromRow, fromColumn + 1, toRow, toColumn, mapMatrix);

        if (right) {
            return true;
        }

        return false;
    }

    public static void Main(string[] args)
    {
        bool[,] mapMatrix = {
            {true, false, false, false},
            {true, false, true, true},
            {true, true, true, true},
            {false, false, false, true}
        };

        Console.WriteLine(RouteExists(0, 0, 3, 3, mapMatrix));
    }
}
```
