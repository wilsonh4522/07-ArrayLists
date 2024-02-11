## Name: Wilson Huang
## Course: APCSA
## Period: 7
## Concept: Unit 7

### Introduction
In APCSA (AP Computer Science A) we are curretly learning about Array List in Java. This unit has so far been challenging but after some background knowldege about arrays in Java unit 6 it was easy to understand but I didn't do to well in the unit 7 exam. Throughout this writeup I will take you through some of my challenges, thinkings, and questions I got wrong on the exam. 

### Challenge #1
One challenge I had when learning unit 7 is understanding what enhanced for loops are and how it is different that a normal for loop. I saw this last unit but I didn't really understand what it was. To answer this I looked at some youtube videos like [this](https://www.youtube.com/watch?v=t8mmNbgKA8w) and searched on the internet. I learned that you use enhanced for loops when you don't need to keep track of the index and regular for loops are good if you want to access an index.
#### Enhanced for loop
```java
int[] numbers = {1, 2, 3, 4, 5};
int sum = 0;
for (int num : numbers) {
    sum += num;
}
```
#### Regular for loop
``` java
int[] numbers = {1, 2, 3, 4, 5};
int sum = 0;
for (int i = 0; i < numbers.length; i++) {
    sum += numbers[i];
}
```
Some of the benefits of an enhanced for loop is that it is easier to write. Therefore making fewer mistakes and it is easier to read. 

### Challenge #2
Anotehr challenge I had when learning unit 7 is understanding the concept of linear searching. I didn't understand what it was and how it could be used. After reading more of the documentation I learned that linear is searching for a specfic value in a group of other values. I also learned that I have been doing ever since learning Java. 
```
for (int i = 0; i < list.size(); i++) // Goes through every index in the array
{
  if (list.get(i).equals(target)) // If one of the arraies is equal to a certain something 
  {
    return i; //If the `if` value is true return the array
  }
}

```
### Challenge #3
In this challenge I will take you through some of the questions I got wrong on the exam and going over it on why I chose it and what the corret  answer is.
#### Challenge #3.1
Consider the following code segment.
```Java
ArrayList<String> musicGenre = new ArrayList<String>();

musicGenre.add("jazz");
musicGenre.add("rocknRoll");
musicGenre.add("hipHop");
musicGenre.add(musicGenre.remove(1));
musicGenre.set(1, musicGenre.remove(1));
System.out.println(musicGenre);
```
What is printed as a result of executing the code segment?
<br>I chose `jazz, rocknRoll` this is wrong because hip hop does not get removed. `jazz, rocknRoll, hipHop` is added then rocknroll is removed and added at then end to get `jazz, hipHop, rocknRoll`. After than `hipHop` gets removed and rocknRoll gets replaced with hipHop because of set method. This is why the answer is `jazz, hipHop`. </br>
#### Challenge #3.2
```Java
public static void doStuff(ArrayList<String> a)
{
  for (int i = 0; i < a.size(); i++)
  {
    a.set(i, a.get(i) + " ");
  }
}

public static void doStuff(int a)
{
  a = a * 2;
}

public static void main(String[] args)
{
  int g = 4;
  doStuff(g);
  System.out.print (g + " ");
  ArrayList<String> list = new ArrayList<String>();
  list.add("banana");
  doStuff(list);
  System.out.print(list);
}
```
What is printed as a result of executing the code segment?
<br>I answered `8 banana`. This is wrong because in the `doStuff` does not change the value of g outside and only inside. So a is equal to 8 in the public `doStuff` but is not in the `main`. The value of g is kept at 4 and does not change. So therefore the answer is `4 banana`. </br> 
#### Challenge #3.3
```Java
// Two nonempty lists of words
private ArrayList<String> list1;
private ArrayList<String> list2;

/** Checks if a String is contained in an ArrayList
* @param aList an ArrayList of String objects
* @param target a String to look for
* @return true if target is in aList; false otherwise
*/
private boolean isIn(ArrayList<String> aList, String target)
{
  for(String s : aList)
  {
    if(s.equals(target))
    {
      return true;
    }
  }
  return false;
}

/** Removes duplicate strings from aList
 * @param aList an ArrayList of String objects
 * @return an ArrayList containing every unique String from aList but
 * not containing any String more than once.
 */
private ArrayList<String> removeDupes(ArrayList<String> aList)
{
  ArrayList<String> output = new ArrayList<String>();
  for(String s : aList)
  {
    if (! isIn(output, s))
    {
      output.add(s);
    }
  }
  return output;
}

/** @return an ArrayList containing each of the elements from list1 and list2
 * but with no duplicate Strings
 */
public ArrayList<String> combiList()
{
  ArrayList<String> uList1 = removeDupes(list1);
  ArrayList<String> uList2 = removeDupes(list2);

  ArrayList<String> result = new ArrayList<String>();

  for (String word : uList1)
  {
    result.add(word);
  }

  for (String word : uList2)
  {
    result.add(word);
  }

  return result;
}
```
The combiList method is intended to return an ArrayList which contains every word which appears on list1 or list2 without any duplicate words. For which of the following values of list1 and list2 will the method not work as intended?

### Takeaways
