## C# and C++

```c#
using System;

public class QuadraticEquation
{
    public static Tuple<double, double> FindRoots(double a, double b, double c)
    {
        double answer1 = (-b + (Math.Sqrt(b*b - 4*a*c))) / (2*a);
        double answer2 = (-b - (Math.Sqrt(b*b - 4*a*c))) / (2*a);

        return Tuple.Create(answer1, answer2);
    }

    public static void Main(string[] args)
    {
        Tuple<double, double> roots = QuadraticEquation.FindRoots(2, 10, 8);
        Console.WriteLine("Roots: " + roots.Item1 + ", " + roots.Item2);
    }
}
```

C++ version

```c++
#include <tuple>
#include <stdexcept>
#include <iostream>
#include <string>
#include <cmath>

std::pair<double, double> findRoots(double a, double b, double c)
{
    double answer1 = (0-b + std::sqrt(b*b - 4*a*c)) / (2*a);
    double answer2 = (0-b - std::sqrt(b*b - 4*a*c)) / (2*a);

    return std::make_pair(answer1, answer2);
}

#ifndef RunTests
int main()
{
    std::pair<double,double> roots = findRoots(2, 10, 8);
    std::cout << "Roots: " + std::to_string(roots.first) + ", " + std::to_string(roots.second);
}
#endif
```
