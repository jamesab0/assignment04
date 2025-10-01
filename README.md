# Python vs C99 Format Comparison
This is a document comparing C99 printf and Python print, both Old-style (%) formatting and F-strings. It will explore integers, floats, and strings formatted in different ways. Proper formatting ensures clean output and sufficient readability.
> String formatting is essential in Python [and C] for creating dynamic and well-structured text by inserting values into strings. <br>
[Source](https://realpython.com/python-string-formatting)


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
## Comparison Table
| Type | Example Code (C) | Example Code (Python) | Output |
|-----|-----|-----|-----|
| int |<pre><code>printf("%5d", 42);</code></pre>|<pre><code>print("%5d" % 42)</code></pre>|<pre>   42</pre>|
| int |<pre><code>printf("%+5d", 42);</code></pre>|<pre><code>print("%+5d" % 42)</code></pre>|<pre>  +42</pre>|
| int |<pre><code>printf("%05d", 42);</code></pre>|<pre><code>print("%05d" % 42)</code></pre>|<pre>00042</pre>|
|float|<pre><code>printf("%8.2f", 3.14159);</code></pre>|<pre><code>print("%8.2f" % 3.14159)</code></pre>|<pre>    3.14</pre>|
|float|<pre><code>printf("%e", 3.14159);</code></pre>|<pre><code>print("%e" % 3.14159)</code></pre>|<pre>3.141590e+00</pre>|
|string|<pre><code>printf("%-10s!", "Hello");</code></pre>|<pre><code>print("%-10s" % "Hello")</code></pre>|<pre>Hello     !</pre>|
|string|<pre><code>printf("%10s!", "Hello");</code></pre>|<pre><code>print("%10s" % "Hello")</code></pre>|<pre>     Hello!</pre>|

---
## Useful Links
[C99 printf documentation](https://en.cppreference.com/w/c/io/fprintf) <br>
[Python old-style % formatting](https://docs.python.org/3/library/stdtypes.html#printf-style-string-formatting) <br>
[Python f-strings](https://docs.python.org/3/reference/lexical_analysis.html#f-strings) <br>

---
## Image
![My Required Image](https://thunderdungeon.com/wp-content/uploads/2024/05/microsoft-office-memes-4-5-21-2024.jpg)
