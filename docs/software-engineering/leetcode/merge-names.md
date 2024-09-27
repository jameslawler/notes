## C# and C++

```c#
using System;
using System.Linq;
using System.Collections.Generic;

public class MergeNames
{
    public static string[] UniqueNames(string[] names1, string[] names2)
    {
        List<string> result = new List<string>();

        foreach (string name1 in names1)
        {
            if (!result.Contains(name1))
            {
                result.Add(name1);
            }
        }

        foreach (string name2 in names2)
        {
            if (!result.Contains(name2))
            {
                result.Add(name2);
            }
        }

        return result.ToArray();
    }

    public static void Main(string[] args)
    {
        string[] names1 = new string[] {"Ava", "Emma", "Olivia"};
        string[] names2 = new string[] {"Olivia", "Sophia", "Emma"};
        Console.WriteLine(string.Join(", ", MergeNames.UniqueNames(names1, names2))); // should print Ava, Emma, Olivia, Sophia
    }
}
```

Alternative with LINQ

```c#
using System;
using System.Linq;

public class MergeNames
{
    public static string[] UniqueNames(string[] names1, string[] names2)
    {
        return names1.Union(names2).ToArray();
    }

    public static void Main(string[] args)
    {
        string[] names1 = new string[] {"Ava", "Emma", "Olivia"};
        string[] names2 = new string[] {"Olivia", "Sophia", "Emma"};
        Console.WriteLine(string.Join(", ", MergeNames.UniqueNames(names1, names2))); // should print Ava, Emma, Olivia, Sophia
    }
}
```

C++

```c++
#include <iostream>
#include <vector>

std::vector<std::string> unique_names(const std::vector<std::string>& names1, const std::vector<std::string>& names2)
{
    std::vector<std::string> names;

    for(auto element : names1)
    {
        if (std::find(names.begin(), names.end(), element) == names.end())
        {
            names.push_back(element);
        }
    }

    for(auto element : names2)
    {
        if (std::find(names.begin(), names.end(), element) == names.end())
        {
            names.push_back(element);
        }
    }

    return names;
}

#ifndef RunTests
int main()
{
    std::vector<std::string> names1 = {"Ava", "Emma", "Olivia"};
    std::vector<std::string> names2 = {"Olivia", "Sophia", "Emma"};

    std::vector<std::string> result = unique_names(names1, names2);
    for(auto element : result)
    {
        std::cout << element << ' '; // should print Ava Emma Olivia Sophia
    }
}
#endif
```
