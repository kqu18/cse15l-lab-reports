**part 1**

The code for my String Server is attached below:
![image](https://user-images.githubusercontent.com/104349171/215583897-14360aac-581b-4eee-9655-8c08337d9d16.png)

The behavior of my code is attached below:
initial page:
![Screenshot 2023-01-30 at 12 08 22 PM](https://user-images.githubusercontent.com/104349171/215584341-2d7c6450-b98e-471c-98bb-72d6f04e6944.jpg)

After first request:
![Screenshot 2023-01-30 at 12 08 33 PM](https://user-images.githubusercontent.com/104349171/215584443-b15902da-182e-45cd-aaa5-ecd8aed6ea5c.jpg)

After second request:
![Screenshot 2023-01-30 at 12 08 42 PM](https://user-images.githubusercontent.com/104349171/215584587-a2dd35f2-755b-4e68-820e-5d0c439ac43b.jpg)


**part 2**


**part 3**

Something I learned in this week's lab is how to properly use JUnit 4 for asserting code. What I did not know before is how to assert whether two doubles are equal. It turned out that 
we need to add an extra parameter *Delta* after the assertion to specify the precision, or the gap between the two doubles.
