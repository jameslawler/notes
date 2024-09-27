## C# & C++

```c#
using System;
using System.Collections.Generic;

public class TrainComposition
{
    LinkedList<int> wagons;

    public TrainComposition()
    {
        wagons = new LinkedList<int>();
    }

    public void AttachWagonFromLeft(int wagonId)
    {
        wagons.AddFirst(wagonId);
    }

    public void AttachWagonFromRight(int wagonId)
    {
        wagons.AddLast(wagonId);
    }

    public int DetachWagonFromLeft()
    {
        int wagonId = wagons.First.Value;
        wagons.RemoveFirst();
        return wagonId;
    }

    public int DetachWagonFromRight()
    {
        int wagonId = wagons.Last.Value;
        wagons.RemoveLast();
        return wagonId;
    }

    public static void Main(string[] args)
    {
        TrainComposition train = new TrainComposition();
        train.AttachWagonFromLeft(7);
        train.AttachWagonFromLeft(13);
        Console.WriteLine(train.DetachWagonFromRight()); // 7
        Console.WriteLine(train.DetachWagonFromLeft()); // 13
    }
}
```

```c++
#include <stdexcept>
#include <iostream>
#include <list>

class TrainComposition
{
private:
    std::list<int> wagons;

public:
    void attachWagonFromLeft(int wagonId)
    {
        wagons.push_front(wagonId);
    }

    void attachWagonFromRight(int wagonId)
    {
        wagons.push_back(wagonId);
    }

    int detachWagonFromLeft()
    {
        int leftWagonId = wagons.front();
        wagons.pop_front();
        return leftWagonId;
    }

    int detachWagonFromRight()
    {
        int rightWagonId = wagons.back();
        wagons.pop_back();
        return rightWagonId;
    }
};

#ifndef RunTests
int main()
{
    TrainComposition train;
    train.attachWagonFromLeft(7);
    train.attachWagonFromLeft(13);
    std::cout << train.detachWagonFromRight() << "\n"; // 7
    std::cout << train.detachWagonFromLeft(); // 13
}
#endif
```
