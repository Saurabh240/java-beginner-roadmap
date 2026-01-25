```java
public class JavaOperator {

    public static void main(String[] args) {

        // Operators

        //Arithmetic Operators
        int a = 10;
        int b = 5;
        System.out.println("Addition: " + (a + b)); // 15
        System.out.println("Subtraction: " + (a - b)); // 5
        System.out.println("Multiplication: " + (a * b)); // 50
        System.out.println("Division: " + (a / b)); // 2
        System.out.println("Modulus: " + (a % b)); // 0

        //Relational Operators
        System.out.println("Equal to: " + (a == b)); // false
        System.out.println("Not equal to: " + (a != b)); // true
        System.out.println("Greater than: " + (a > b)); // true
        System.out.println("Less than: " + (a < b)); // false
        System.out.println("Greater than or equal to: " + (a >= b)); // true
        System.out.println("Less than or equal to: " + (a <= b));

        // Logical Operators
        boolean x = true;
        boolean y = false;
        System.out.println("Logical AND: " + (x && y)); // false
        System.out.println("Logical OR: " + (x || y)); // true
        System.out.println("Logical NOT: " + (!x)); // false

        // Assignment Operators
        int c = 20;
        c += 5; // c = c + 5
        System.out.println("c after += 5: " + c); // 25
        c -= 3; // c = c - 3
        System.out.println("c after -= 3: " + c); // 22
        c *= 2; // c = c * 2
        System.out.println("c after *= 2: " + c); // 44
        c /= 4; // c = c / 4
        System.out.println("c after /= 4: " + c); // 11
        c %= 3; // c = c % 3
        System.out.println("c after %= 3: " + c); // 2

    }
}
```

```java
public class JavaControl {
    public static void main(String[] args) {

        int marks = 55;

        if (marks >= 90) {
            System.out.println("Grade A");
        } else if (marks >= 75) {
            System.out.println("Grade B");
        } else if (marks >= 60) {
            System.out.println("Grade C");
        } else {
            System.out.println("Grade F");
        }

        // Switch statement example
        int day = 8;

        switch (day) {
            case 1:
                System.out.println("Monday");
                break;
            case 2:
                System.out.println("Tuesday");
                break;
            case 3:
                System.out.println("Wednesday");
                break;
            case 4:
                System.out.println("Thursday");
                break;
            case 5:
                System.out.println("Friday");
                break;
            case 6:
                System.out.println("Saturday");
                break;
            case 7:
                System.out.println("Sunday");
                break;
            default:
                System.out.println("Invalid day");
        }

        int n = 30;

        if(n % 15 ==0){
            System.out.println("FIZZBUZZ");
        } else if(n % 3 ==0){
            System.out.println("FIZZ");
        } else if(n % 5 ==0){
            System.out.println("BUZZ");
        } else{
            System.out.println(n);
        }

     // Printing Even Odd
     // Switch case days of week
     // FIZZ BUZZ problem
    }
}
```

```java
public class JavaLoop {
    public static void main(String[] args) {
        // For Loop
        for (int i = 5; i >= 0; i--) {
            System.out.println("Iteration: " + i); // 5 4 3 2 1 0
        }

        // While Loop
        int i = 5;
        while (i >= 0) {
            System.out.println("Iteration: " + i); // 5 4 3 2 1 0
            i--;
        }

        // Do-While Loop
        int j = 5;
        do {
            System.out.println("Iteration: " + i); // 5 4 3 2 1 0
            j--;
        } while (j >= 0);

        // Print 1 to 10 using For Loop
        for (int k = 1; k<=10;k++) {
            System.out.print(k + " ");
        }

        // Sum of first 10 natural numbers

    }
}
```

```java
public class JavaArrays {

    public static void main(String[] args) {
        // Declare and initialize an array
        int[] numbers = {10, 20, 30, 40, 50}; // 0 to (n-1)


        // Access and print elements of the array
        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Element at index " + i + ": " + numbers[i]);
        }

        // Calculate the sum of the array elements
        int sum = 0;
        for (int number : numbers) {
            sum += number; // sum = sum + number
        }
        System.out.println("Sum of array elements: " + sum);

        String[] fruits = {"Apple", "Banana", "Cherry", "Date", "Elderberry"};

        // Access and print elements of the array
        for (int i = 0; i < fruits.length; i++) {
            System.out.println("Element at index " + i + ": " + fruits[i]);
        }

        // Print all fruits
        for (String fruit : fruits) {
            System.out.println(fruit);
        }

        // Find Max and Min in an array
        int[] values = {45, 22, 89, 12, 67 };

        // Reverse an array
    }
}
```

```java
public class Java2DArray {

    public static void main(String[] args) {
        int[][] array2D = {
                {1, 2, 3},
                {4, 5, 6},
                {7, 8, 9}
        };

        for (int i = 0; i < array2D.length; i++) {
            for (int j = 0; j < array2D[i].length; j++) {
                System.out.print(array2D[i][j] + " ");  // i = 0 j=0
            } // Time complexity O(n^2)
            System.out.println();
        }
    }
}
```

```java
public class JavaString {
    public static void main(String[] args) {
        String str1 = "Hello, World!";
        String str2 = "Hello, World!";
        String str3 = new String("Hello, World!");

        // Comparing references
        System.out.println("str1 == str2: " + (str1 == str2)); // true, same reference in string pool
        System.out.println("str1 == str3: " + (str1 == str3)); // false, different references

        // Comparing values
        System.out.println("str1.equals(str2): " + str1.equals(str2)); // true, same content
        System.out.println("str1.equals(str3): " + str1.equals(str3)); // true, same content

        // String methods
        System.out.println("Length of str1: " + str1.length());
        System.out.println("Char at index 7 of str1: " + str1.charAt(7));
        System.out.println("Index of 'World' in str1: " + str1.indexOf("W"));
        System.out.println("Substring of str1 (7, 12): " + str1.substring(7, 12));
        System.out.println("Uppercase str1: " + str1.toUpperCase());
        System.out.println("Replace 'World' with 'Java': " + str1.replace("World", "Java"));

        // Reversing a string
        // Pallindrome check ("madam")
    }
}
```
```java
public class JavaMethod {
    public static void main(String[] args) {
        System.out.println(add(5, 3));
        System.out.println(subtract(5, 3));
        System.out.println(multiply(5, 3));
        System.out.println(divide(5, 0));
    }

    public static int add(int a, int b) {
        return a + b;
    }

    public static int subtract(int a, int b) {
        return a - b;
    }

    public static int multiply(int a, int b) {
        return a * b;
    }

    public static double divide(int a, int b) {
        if (b == 0) {
            throw new IllegalArgumentException("Division by zero is not allowed.");
        }
        return (double) a / b;
    }

    // Factorial method
    // 5! = 5 * 4 * 3 * 2 * 1 = 120
    // Fibonacci method
    // Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8, 13, 21, ...
}
```
