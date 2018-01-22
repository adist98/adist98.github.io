### Stress Testing (Maximum Pairwise Product - AlgoToolBox)
#### Excerpt of code

```c++
while (true) {
  int n = rand() % 10 + 2;
  cerr << n << "\n";
  vector<int> a;
  for (int i = 0; i < n; ++i) {
    a.push_back(rand() % 100000);
  }
  for (int i = 0; i < n; ++i) {
    cerr << a[i] << ' ';
  }
  cerr << "\n";
  long long res1 = MaxPairwiseProduct(a);
  long long res2 = MaxPairwiseProductFast(a);
  if (res1 != res2) {
    cerr << "Wrong answer: " << res1 << ' ' << res2 << "\n";
    break;
  }
  else {
    cerr << "OK\n";
  }
}
```
