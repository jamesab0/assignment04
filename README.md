# Python vs C99 Format Comparison
This is a document comparing C99 printf and Python print.
> This is a block quote


---
## Integer Formatting
### C99 printf
```C
int main()
{
  int n = 42;
  printf("%5d\n", n); // width 5, right-aligned
  printf("%+5d\n", n); // width 5, show sign
  printf("%05d\n", n); // width 5, pad with zeros
  return 0;
}
```

### Python print
