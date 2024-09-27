## C#

```c#
using System;

public class BoatMovements
{
    private static bool IsOutOfBounds(bool[,] gameMatrix, int row, int column)
    {
        if (row < 0 || row >= gameMatrix.GetLength(0)) {
            return true;
        }

        if (column < 0 || column >= gameMatrix.GetLength(1)) {
            return true;
        }

        return false;
    }

    private static bool IsAllowedMove(int fromRow, int fromColumn, int toRow, int toColumn)
    {
        bool isLeftMove = fromRow == toRow && toColumn == fromColumn - 1;
        bool isUpMove = toRow == fromRow - 1 && toColumn == fromColumn;
        bool isDownMove = toRow == fromRow + 1 && toColumn == fromColumn;
        bool isRightMove = fromRow == toRow && (toColumn == fromColumn + 1 || toColumn == fromColumn + 2);

        return isLeftMove || isUpMove || isDownMove || isRightMove;
    }

    public static bool CanTravelTo(bool[,] gameMatrix, int fromRow, int fromColumn, int toRow, int toColumn)
    {
        if (IsOutOfBounds(gameMatrix, fromRow, fromColumn)) {
            return false;
        }

        if (IsOutOfBounds(gameMatrix, toRow, toColumn)) {
            return false;
        }

        if (!IsAllowedMove(fromRow, fromColumn, toRow, toColumn)) {
            return false;
        }

        if (toColumn > fromColumn + 1) {
            return gameMatrix[toRow, toColumn - 1] && gameMatrix[toRow, toColumn];
        }

        return gameMatrix[toRow, toColumn];
    }

    public static void Main()
    {
        bool[,] gameMatrix =
        {
            {false, true,  true,  false, false, false},
            {true,  true,  true,  false, false, false},
            {true,  true,  true,  true,  true,  true},
            {false, true,  true,  false, true,  true},
            {false, true,  true,  true,  false, true},
            {false, false, false, false, false, false},
        };

        Console.WriteLine(CanTravelTo(gameMatrix, 3, 2, 2, 2)); // true, Valid move
        Console.WriteLine(CanTravelTo(gameMatrix, 3, 2, 3, 4)); // false, Can't travel through land
        Console.WriteLine(CanTravelTo(gameMatrix, 3, 2, 6, 2)); // false, Out of bounds
    }
}
```
