### 01 A number into String/Char Array of digits
```java 
int number = 12345;
char[] digits = String.valueOf(number).toCharArray();

int number = 12345;
String[] digits = String.valueOf(number).split("");
```


### 02 Array String into Integer Array
```java 
 String [] str = {"123", "345", "437", "894"};
      int size = str.length;
      int [] arr = new int [size];
      for(int i=0; i<size; i++) {
         arr[i] = Integer.parseInt(str[i]);
      }
```

### 03 Integer List ot Integer Array
```java
List<Integer> list = new ArrayList<Integer>();
		list.add(1);
		list.add(2);
		list.add(3);
		list.add(4);
		list.add(5);
		int[] arr = list.stream().mapToInt(i->i).toArray();
```

### 04 Integer as String into BigInteger
```java
String str = “123456789”;
BigInteger C = new BigInteger(str);
```

### 05 Integer into BigInteger
```java
int val  = 123456789;
BigInteger C = BigInteger.valueOf(val);
```

### 06 Function to convert Set of Integer to primitive int Array 
```java
 public static int[] convertIntSetToStringSet( 
        Set<Integer> setOfInteger) 
 { 
  return setOfInteger.stream() 
   .mapToInt(Integer::intValue) 
   .toArray(); 
 } 
 //The Integer::intValue method reference is used to convert each Integer to its corresponding int.
 ```

 ### 07 Function to convert Set of Integer to Set of String 
```java
Set<Integer> setOfInteger = new HashSet<>(
            Arrays.asList(1, 2, 3, 4, 5));

 // Convert Set of integers to set of String
        Set<String> setOfString = setOfInteger.stream()
                    .map(String::valueOf)
                    .collect(Collectors.toSet());

```

 ### 08 convert set of String to set of Integer
 ```java
 Set<String> setOfString = new HashSet<>( 
            Arrays.asList("1", "2", "3", "4", "5")); 
  
// Convert Set of String to set of Integer 
Set<Integer> setOfInteger = setOfString.stream() 
					.map(s -> Integer.parseInt(s)) 
					.collect(Collectors.toSet()); 
```

### 09 convert int/number into int array
```java
int arr[] =  Arrays.stream(String.valueOf(1223).split("")) 
                     .mapToInt(Integer::parseInt) 
                     .toArray();
```

### 10 conver int/number into integer list
```java
List<Integer> intNums = Arrays.stream(stringNum)
                                .map(Integer::parseInt)
                                .collect(Collectors.toList());
```
> !NOTE
>we used `map` and not `mapToInt` 
>`map(Integer::parseInt)` returns a `Stream<Integer>`, not an `IntStream`.
>
>`mapToInt` returns `IntStream`. But `IntStream` doesn't have a `collect()` method that accepts a Collector and thus `IntStream` cannot use `collect(Collectors.toList())`.
>
still to use collector for `mapToInt`  
```java
List<Integer> intNums = Arrays.stream(stringNum)
      .mapToInt(Integer::parseInt)
       .collect(ArrayList::new,ArrayList::add,ArrayList::addAll);```
								
 