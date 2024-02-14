# **Lab 3** 
## **Part 1 - Bugs**

![Image](faulty.png)
This is the `ArrayExamples.java` class that we were provided during the lab which contains three buggy methods that produces the wrong output given certain inputs. The bug that I will be focusing on in this lab report is the `averageWithoutLowest()` method.

**Faliure inducing input:** 
`double[] input1 = {1,1,2,4};
double average1 = ArrayExamples.averageWithoutLowest(input1);
assertEquals(3.0, average1);`

This input produces a faulty output because when diving to get the average of the numbers, the program does not account for multiple "lowest" being removed, only one of them.
