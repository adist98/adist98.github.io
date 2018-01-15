## Maximum Pairwise Product (Algo Toolbox - CERA)

Note : It is advised that everybody values Coursera's code of conduct and qualifies each assignment by himself/herself.This Github page is created for personal use.
```c++
#include <iostream>
#include <vector>

using std::vector;
using std::cin;
using std::cout;

int MaxPairwiseProduct(const vector<int>& numbers) {
  int result = 0;
  int n = numbers.size();
  for (int i = 0; i < n; ++i) {
    for (int j = i + 1; j < n; ++j) {
      if (numbers[i] * numbers[j] > result) {
        result = numbers[i] * numbers[j];
      }
    }
  }
  return result;
}

int main() {
    int n;
    cin >> n;
    vector<int> numbers(n);
    for (int i = 0; i < n; ++i) {
        cin >> numbers[i];
    } 

    int result = MaxPairwiseProduct(numbers);
    cout << result << "\n";
    return 0;
}
```
