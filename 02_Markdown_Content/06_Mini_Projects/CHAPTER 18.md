CHAPTER 18 – BUBBLE SORT

We already studied about Bubble Sort before, now it’s the implementation
project!

Follow these steps :D

1)  Create a new folder 🡪 “BubbleSortProject”

    <img src="CHAPTER18_media/media/image1.png"
    style="width:1.22229in;height:1.79208in" />
    <img src="CHAPTER18_media/media/image2.png"
    style="width:1.44452in;height:0.83338in" />
    <img src="CHAPTER18_media/media/image3.png"
    style="width:1.98621in;height:0.35419in" />

2)  Create a New File in VS Code 🡪 “main.py”

    <img src="CHAPTER18_media/media/image4.png"
    style="width:2.54047in;height:2.37624in" />
    <img src="CHAPTER18_media/media/image4.png"
    style="width:1.48515in;height:0.44467in" />

    <img src="CHAPTER18_media/media/image5.png"
    style="width:6.22949in;height:0.81254in" />

3)  Enter Title

    <img src="CHAPTER18_media/media/image6.png"
    style="width:5.12526in;height:1.41674in" />

    Output:

    <img src="CHAPTER18_media/media/image7.png"
    style="width:4.31967in;height:2.22928in" />

    Explanation

- print() displays text in the terminal.

- The lines of equal signs make the program title easier to distinguish.

- This is the introduction displayed whenever the program starts.

4)  Enter Numbers

    Add codes as below:

    <img src="CHAPTER18_media/media/image8.png"
    style="width:5.46556in;height:2.56958in" />

    Output:

    <img src="CHAPTER18_media/media/image9.png"
    style="width:4.06271in;height:2.29178in" />

    Explanation:

- input() receives information entered by the user.

- split() separates the numbers whenever there is a space.

- int() converts each input into an integer.

- The list comprehension stores the converted numbers in a Python list.

5)  Ask user to choose sorting order

    2 choices : Ascending order (smallest to largest) and Descending
    order (largest to smallest)

    Add codes as below:

    <img src="CHAPTER18_media/media/image10.png"
    style="width:4.278in;height:2.56958in" />

    Explanation:

    The if and elif statements check which option the user selects.

- ascending = True tells the sorting function to arrange numbers from
  smallest to largest.

- ascending = False tells it to arrange numbers from largest to
  smallest.

- exit() ends the program if the user enters an invalid option.

6)  Define Bubble Sort function

    Add codes as below:

    <img src="CHAPTER18_media/media/image11.png"
    style="width:5.73641in;height:5.84058in" />

    <img src="CHAPTER18_media/media/image12.png"
    style="width:5.84058in;height:3.00015in" />

    This is the main function of our project now 🡪 the function that
    will process numbers and sort it with Bubble Sort

    Explanation:

- Create the copy of the original list

  <img src="CHAPTER18_media/media/image13.png"
  style="width:1.98597in;height:0.28713in" />

- Initialize the counters

  <img src="CHAPTER18_media/media/image14.png"
  style="width:1.38614in;height:0.75039in" /> These variables keep track
  of how many comparisons, swaps, and passes are performed.

- Outer loop

  <img src="CHAPTER18_media/media/image15.png"
  style="width:2.78383in;height:0.27723in" /> 🡪 Controls how many passes
  the algorithm performs

  A list with n elements, maximum number of passes is n-1

- Inner Loop

  <img src="CHAPTER18_media/media/image16.png"
  style="width:2.74257in;height:0.27723in" /> The inner loop compares
  adjacent elements.

  The - i part reduces the number of comparisons after each pass because
  the elements at the end of the list are already in their correct
  positions.

- Compare Elements

  <img src="CHAPTER18_media/media/image17.png"
  style="width:2.69307in;height:0.92462in" />

  The program checks whether the two adjacent elements are in the wrong
  order.

  For ascending order, swap if the left element is greater.

  For descending order, swap if the left element is smaller.

- Swap the Elements

  <img src="CHAPTER18_media/media/image18.png"
  style="width:3.0033in;height:0.27723in" />

- Stop when no swaps occur

  <img src="CHAPTER18_media/media/image19.png"
  style="width:1.30932in;height:0.58416in" />

7)  Display Final Result

    <img src="CHAPTER18_media/media/image20.png"
    style="width:5.29194in;height:4.00021in" />

    Explanation:

- bubble_sort(numbers, ascending) calls the sorting function.

- The function returns four values: the sorted list, comparisons, swaps,
  and passes.

- The program displays the final results and performance statistics.

8)  Combine All the Codes!!! Then Click Run and Debug to run the codes

    <img src="CHAPTER18_media/media/image21.png"
    style="width:3.6113in;height:3.22933in" />

9)  The Result/Output

    <img src="CHAPTER18_media/media/image22.png"
    style="width:3.68987in;height:6.11881in" />

    <img src="CHAPTER18_media/media/image23.png"
    style="width:3.62376in;height:3.27767in" />

    CONGRATZZZZ!!!

    You have completed a Bubble Sort project using Python :D

    The project demonstrates how an algorithm can be translated into a
    working program through loops, conditional statements, functions,
    and lists.
