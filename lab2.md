**part 1**

The code for my String Server is attached below:
![image](https://user-images.githubusercontent.com/104349171/215583897-14360aac-581b-4eee-9655-8c08337d9d16.png)

The behavior of my code is attached below:
initial page:
![Screenshot 2023-01-30 at 12 08 22 PM](https://user-images.githubusercontent.com/104349171/215584341-2d7c6450-b98e-471c-98bb-72d6f04e6944.jpg)

After first request:
![Screenshot 2023-01-30 at 12 08 33 PM](https://user-images.githubusercontent.com/104349171/215584443-b15902da-182e-45cd-aaa5-ecd8aed6ea5c.jpg)

In this request, the method `handleRequest` is called. The input is `http://localhost:4000/add-message?s=Herllo`.

The method extracts `?s=Herllo` as the query, and then the code splits the input and saves the string after the `=`.

So we now have `"Herllo"` as our `parameter[1]`, so we concatenate it to the initial string, which is empty. 

So we have the string `"Herllo"` in the webpage. 


After second request:
![Screenshot 2023-01-30 at 12 08 42 PM](https://user-images.githubusercontent.com/104349171/215584587-a2dd35f2-755b-4e68-820e-5d0c439ac43b.jpg)

In this request, similarly, the method `handleRequest` is called. The input is `http://localhost:4000/add-message?s=another_String`.

The method extracts `?s=another_String` as the query, and then the code splits the input and saves the string after the `=`.

So we now have `"another_String"` as our `parameter[1]`, so we concatenate it to the initial string, which is `Herllo`.

So we now made changes to the initial string value and we have:
`"Herllo",
"another_String"` in the webpage.


**part 2**

Junit code that tests for bugs for ArrayExamples.java:

```
  @Test
  public void testReverseInPlace2(){
    int[] input1 = {1,2,3};
    ArrayExamples.reverseInPlace(input1);
    assertEquals(input1[0], 3);
    assertEquals(input1[1], 2);
    assertEquals(input1[2], 1);
  }
```
```
  @Test
  public void testReverse2(){
    int[] input1 = {1,2,3};
    int[]output = ArrayExamples.reversed(input1);
    assertEquals(output[0], 3);
    assertEquals(output[1], 2);
    assertEquals(output[2], 1);
  }
```

Junit code that will not induce an error:

```
 @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```

Symptoms from the inputs:

![Screenshot 2023-01-30 at 2 16 20 PM](https://user-images.githubusercontent.com/104349171/215608162-4e438ccd-fb23-424d-9329-39f57e3e26f5.jpg)



The following changes have been made to the original code to fix bugs:

![image](https://user-images.githubusercontent.com/104349171/215607788-bc53c80e-e49c-4376-a756-dd4b05c4c9cf.png)

for reverseInPlace, 

**part 3**

Something I learned in this week's lab is how to properly use JUnit 4 for asserting code. What I did not know before is how to assert whether two doubles are equal. It turned out that 
we need to add an extra parameter *Delta* after the assertion to specify the precision, or the gap between the two doubles.
