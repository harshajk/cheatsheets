# Loop vectorization

```C
void copy(short x[][100], const short y[][100]) {
  int i, j;
  for (i = 0; i < 30; i++) 
  {
    for (j = 0; j < 100; j++) 
    {
      x[i][j] = y[i][j];
    }
  }
}
```
