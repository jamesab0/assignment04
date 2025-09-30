# Python vs C99 Format Comparison
This is a document comparing C99 printf and Python print.
> This is a block quote


---
## Integer Formatting
### C99 printf
```C
#include <stdio.h>

int main()
{
  int n = 42;
  printf("%5d\n", n); // width 5, right-aligned
  printf("%+5d\n", n); // width 5, show sign
  printf("%05d\n", n); // width 5, pad with zeros
  return 0;
}
```
#### Output:
```C
   42
  +42
00042
```

### Python print
#### Old-style (%) formatting
```Python
n = 42
print("%5d" % n)   # width 5, right-aligned
print("%+5d" % n)  # width 5, show sign
print("%05d" % n)  # width 5, pad with zeroes
```
#### F-strings
```Python
n = 42
print(f"{n:5}")  # width 5, right-aligned
print(f"{n:+5}") # width 5, show sign
print(f"{n:05}") # width 5, pad with zeros
```
#### Output:
```Python
   42
  +42
00042
```

---
## Float Formatting
### C99 printf
```C
#include <stdio.h>

int main()
{
  float f = 3.14159;
  printf("%8.2f\n", f);  // width 8, 2 decimals
  printf("%08.2f\n", f); // width 8, pad with zeros
  printf("%e\n", f);     // scientific notation
  return 0;
}
```
#### Output:
```C
    3.14
00003.14
3.141590e+00
```
### Python print
#### Old-style (%) formatting
```Python
f = 3.14159
print("%8.2f" % f)   # width 8, 2 decimals
print("%08.2f" % f)  # width 8, pad with zeroes
print("%e" % f)      # scientific notation
```
#### F-strings
```Python
f = 3.14159
print(f"{f:8.2f}")   # width 8, 2 decimals
print(f"{f:08.2f}")  # width 8, pad with zeroes
print(f"{f:e}")      # scientific notation
```
#### Output:
```Python
    3.14
00003.14
3.141590e+00
```

---
## String Formatting
### C99 printf
```C
#include <stdio.h>

int main() {
  char s[] = "Hello";
  char t[] = "World";
  printf("%-10s!\n", s); // width 10, left-aligned
  printf("%10s!\n", s);  // width 10, right-aligned
  strcat(s, t);
  printf("%s\n", s);     // concatenate strings
  return 0;
}
```
#### Output:
```C
Hello     !
     Hello!
HelloWorld
```
### Python print
#### Old-style (%) formatting
```Python
s = "Hello"
print("%-10s!" % s)                                # width 10, left-aligned
print("%10s!" % s)                                 # width 10, right-aligned
print("%*s" % (10 - (10 - len(s)) // 2, s), "!")   # width 10, center-aligned
```
#### Output:
```Python
Hello     !
     Hello!
  Hello  !
```
#### F-strings
```Python
s = "Hello"
t = "World"
print(f"{s:<10}!")   # width 10, left aligned
print(f"{s:>10}!")   # width 10, right aligned
print(f"{s:^10}!")   # width 10, center aligned
print(f"{s:0>10}!")  # width 10, pad with zeroes
print(s + t)         # concatenate strings
```
#### Output:
```Python
Hello     !
     Hello!
  Hello   !
00000Hello!
HelloWorld
```

---
| Type | Example Code (C) | Example Code (Python) | Output |
|------|
