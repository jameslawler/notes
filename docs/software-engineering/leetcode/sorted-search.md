## C#

```c#
using System;

public class SortedSearch
{
    public static int CountNumbers(int[] sortedArray, int lessThan)
    {
        int startIndex = 0;
        int endIndex = sortedArray.Length - 1;
        int middleIndex = 0;

        while (startIndex <= endIndex)
        {
            middleIndex = startIndex + ((endIndex - startIndex) / 2);
            int middleValue = sortedArray[middleIndex];

            if (middleValue == lessThan)
            {
                return middleIndex;
            }

            if (middleValue < lessThan)
            {
                startIndex = middleIndex + 1;
            }

            if (middleValue > lessThan)
            {
                endIndex = middleIndex - 1;
            }

        }

        if (sortedArray[middleIndex] >= lessThan) {
            return middleIndex;
        } else {
            return middleIndex + 1;
        }
    }

    public static void Main(string[] args)
    {
        Console.WriteLine(SortedSearch.CountNumbers(new int[] { 1, 3, 5, 7 }, 4));
    }
}
```
