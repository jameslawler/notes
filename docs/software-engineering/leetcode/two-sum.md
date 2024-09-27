## C++

```c++
#include <stdexcept>
#include <iostream>
#include <vector>
#include <utility>
#include <map>

std::pair<int, int> findTwoSum(const std::vector<int>& list, int sum)
{
  int index = 0;
  std::map<int, int> left;
  std::pair<int, int> result;

  for (int item : list) {
      if (item <= sum) {
          if (left.contains(item)) {
              result.first = left[item];
              result.second = index;
              return result;
          }
          int leftOver = sum - item;
          left[leftOver] = index;
          index++;
      }
  }

  result.first = -1;
  result.second = -1;

  return result;

}

#ifndef RunTests
int main()
{
  std::vector<int> list = {3, 1, 5, 7, 5, 9};
  std::pair<int, int> indices = findTwoSum(list, 10);
  std::cout << indices.first << '\n' << indices.second;
}
#endif
```
