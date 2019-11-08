# JavaNotes
Java NOtes and cheat sheet I wrote during work and academia

Generic Java
---------------------
### HashMap vs TreeMap
```java
HashMap: the hash map we know

TreeMap: maintain a red-black tree internally, not O(1) lookup, but gives you a sorted keys
```
### LinkedHashMap
```java
Extends HashMap, maintain a linked list internally,
useful for `LRU` type problem.
Leetcode #146
```
###  ArrayList
ArrayList is implemented based on primitive array 

Feature: 
ArrayList<T> myarrlist = new ArrayList<T>()
#### 1.Type Satety
ArrayList provides stronger type safety ensurance than array
  
https://coderanch.com/t/625190/certification/Array-ArrayList-Thread-safety-Type

#### 2. Flexibility
ArrayList has Dynamic, and a better interface

#### 3. Size vs length
arraylist.size() is the actually length
array.length is the actually capacity of array

#### 4. Multi-dimension
arraylist doesn't support multi-dimension, array does

#### 5, primitive types
ArrayList doesn't support primitive types

### Multi-threading
Primitive types gurantees thread-safety
Immutable objects are thread-safe, but mutable objects are not.
For example, String is thread-safe, Stringbuffer is not.


### String pool
```java
String str1 = new string("abc") // allocate space on heap, put it in string pool, return reference from  heap
String str2 = "abc" // search in string pool to find if same string exists, by method "equals", return reference from string pool
obvisouly, str1.equals(str2) == True 
but, str1 != str2, as str1 refer to heap, str2 refer to string pool

String str3 = "abc"
str2 = str3, as both refer to string pool

str1 = str1.intern() 
// if string pool contains the object str1 is referring(on heap), refer to string pool instead of heap. ojbect on heap will go to GC 
now str2 = str1 = str3

// string concate
a + b, if both constant, consider as string literal
a + b, if either is not constant, consider as variable, use new String()
```

###  Array
```java
#array copy
import java.util.Arrays;

int a[]={10,20,30,40,50};
int b[]=new int[a.length];

b = a // shallow copy, only copy reference

b=Arrays.copyOf(a,a.length); ////copying one array to another

#2d array
int[][] wrong = new int[][]; // not OK, you must specify 1st dimension
int[][] right = new int[2][]; // OK

```



###  Queue
```java
add element: 
add(), throw exception when out of bound
offer(), return false when out of bound

remove first:
remove(), throw excption when empty
poll(), return null when empty

lookup first:
element(),
peek()
```

### 6. Regex
`\\s` will match whitespace, AND space

mvn tips
---------------------

### 1. check style
https://maven.apache.org/plugins/maven-checkstyle-plugin/usage.html
