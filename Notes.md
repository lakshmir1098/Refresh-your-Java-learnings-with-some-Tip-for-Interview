## 01 Big Integer
1. BigInteger class is used for the mathematical operation which involves very big integer calculations that are outside the limit of all available primitive data types.
2. Mathematical operations :
    
    add(),subtract(), multiply(), divide(), remainder() 

    >instead of,
    >`int c = a + b;`
    >we use on BigInteger as,
    >`BigInteger C = A.add(B);`
    >
    >for comparision
    >
    >`if (a < b) {}  `       // For primitive int
    >
    >`if (A.compareTo(B) < 0)  {}` // For BigInteger 
    >
    > for equal
    > `if (A.equals(B)) {}`
    >
    
3. In the BigInteger class in Java, both the mod and modPow methods are used for modular arithmetic, but they serve different purposes.
    * The `mod` method computes the modulus (or remainder) of one BigInteger divided by another.
        ```java
            BigInteger a = new BigInteger       ("12345678901234567890");
            BigInteger b = new BigInteger("100");
            BigInteger result = a.mod(b);
        ```
    * The `modPow` method calculates the result of raising a BigInteger to a power (exponentiation) and then taking the modulus with respect to another BigInteger
        ```java
        BigInteger base = new BigInteger("2");
        BigInteger exponent = new BigInteger("10");
        BigInteger modulus = new BigInteger("1000");
        BigInteger result = base.modPow(exponent, modulus);
        ````
    *  If you want to calculate __base<sup>exponent </sup>__  without a modulus, you would typically do that by multiplying the BigInteger in a loop or using a recursive method.
        ```java
        BigInteger result = BigInteger.ONE;
            for (int i = 0; i < exponent; i++) {
                result = result.multiply(base);
            }
        ```
        or
        ```java
        public static BigInteger exponentiate(BigInteger base, int exponent) {
            if (exponent == 0) {
                return BigInteger.ONE; // Base case: anything raised to the power of 0 is 1
            } else {
                return base.multiply(exponentiate(base, exponent - 1));
            }
        }
        ```

4. BigInteger has BigInteger.TEN, BigInteger.ONE, BigInteger.ZERO to represent 10,1,0 int values.

## 02 HashMap

HashMap is a part of Java’s collection.t allows to store the null keys as well, but there should be only one null key object and there can be any number of null values. This class makes no guarantees as to the order of the map. To use this class and its methods, you need to import java.util.HashMap package.HashMaps allow for duplicate values, but not duplicate keys.If you try to insert the duplicate key in HashMap, it will replace the element of the corresponding key. 

` HashMap<Integer, String> hm = new HashMap<>();`

1.  Adding Elements in HashMap
  ```hm.put(1, "Geeks");```

2. Changing Elements in HashMap
`hm.put(2, "For");`

3. Removing Element
 `hm.remove(4);`

4. Traversal
```java
for (Map.Entry<String, Integer> e : map.entrySet())
    System.out.println("Key: " + e.getKey() + " Value: " + e.getValue()); 
```

## 03 ConcurrentHashMap
Same as HashMap but with some additional features such as such as `putIfAbsent()`, `replace()` and different way of traversing. Unliks `HashMap` it doesn't allow null kay and value

`ConcurrentHashMap<String, Integer> map = new ConcurrentHashMap<>();
`

1. `map.get(key)` to get the value for the provided key
2. putIfAbsent()
```java
ConcurrentHashMap<Integer, String> m
            = new ConcurrentHashMap<>();
 
        // Insert mappings using
        // put method
        m.put(100, "Hello");
        m.put(101, "Geeks");
        m.put(102, "Geeks");
 
        // Here we cant add Hello because 101 key
        // is already present in ConcurrentHashMap object
        m.putIfAbsent(101, "Hello");
 
        // We can remove entry because 101 key
        // is associated with For value
        m.remove(101, "Geeks");
 
        // Now we can add Hello
        m.putIfAbsent(103, "Hello");
```
3. `chmp2.putAll(chmp1)` to copy all keys and avlues from one ConcurrentHashMap to another.
4. Traversal
```java
ConcurrentHashMap<Integer, String> chmap
            = new ConcurrentHashMap<Integer, String>();
// Create an Iterator over the
        // ConcurrentHashMap
Iterator<ConcurrentHashMap.Entry<Integer, String> >
    itr = chmap.entrySet().iterator();

// The hasNext() method is used to check if there is
// a next element The next() method is used to
// retrieve the next element
while (itr.hasNext()) {
    ConcurrentHashMap.Entry<Integer, String> entry
        = itr.next();
    System.out.println("Key = " + entry.getKey()
                        + ", Value = "
                        + entry.getValue());
}
```
## 04 
