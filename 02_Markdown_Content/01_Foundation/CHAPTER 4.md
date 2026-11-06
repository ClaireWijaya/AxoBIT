Chapter 4 Introduction to Data Structures

1.  What data structures are?

- Data structures are ways to organize and store data in a computer so
  it’s easy to access and manage 🡪 Important tools in programming

- The following are some of <span class="mark">the widely used data
  structures:</span>

> <img src="CHAPTER4_media/media/image1.jpg"
> style="width:2.11521in;height:1.82437in" />

1.  Arrays

    Arrays are basic data structures that store multiple items of the
    same type in one memory block.

    <img src="CHAPTER4_media/media/image2.jpg"
    style="width:4.07639in;height:1.79167in" />

    Each element in an array can be accessed using an index, which
    represents its position. In most programming languages, array
    indexing starts from 0.

| Index | 0   | 1   | 2   | 3   | 4   | 5   |
|:------|:----|:----|:----|:----|:----|:----|
| Array | 5   | 12  | 7   | 1   | 8   | 17  |

> For example, accessing index 2 gives the value 30.

2.  Linked List

    Another frequent data structure is linked lists, which are made up
    of a sequence of nodes (as shown in the figure) connected by links.

    <img src="CHAPTER4_media/media/image3.jpg"
    style="width:3.54861in;height:1.68056in" />

    Each node in a linked list typically contains two parts:

- **Data:** Stores the actual value.

- **Link (Pointer):** Stores a reference to the next node.

> The last node points to NULL, indicating that there are no more nodes
> in the sequence.

1.  Stacks and Queues

    Stacks and queues are linear data structures that organize data
    based on specific order principles.

- Stacks (LIFO – Last In, First Out)

  LIFO = The last element added to the stack is the first one to be
  removed.

  For example, a stack of plates!! In a canteen, you will take the last
  plate placed on top right? So it is the first plate taken away.

  Two common stack operations are:

<!-- -->

- **Push:** Adds an element to the top of the stack

- **Pop:** Removes the top element from the stack

> <img src="CHAPTER4_media/media/image4.jpg"
> style="width:2.51389in;height:1.67361in" />

- Queues (FIFO – First In, First Out)

  FIFO = The first element added to the queue is the first one to be
  removed.

  For example, people waiting in a line are generally served in the
  order they arrive!!

  Two common queue operations are:

<!-- -->

- **Enqueue:** Adds an element to the rear of the queue.

- **Dequeue:** Removes an element from the front of the queue.

> <img src="CHAPTER4_media/media/image5.jpg"
> style="width:3.13194in;height:1.29167in" />

1.  Trees

    A tree is a nonlinear data structure consisting of nodes connected
    by edges in a hierarchical structure, starting from a root node and
    extending into branches of other nodes.

    <img src="CHAPTER4_media/media/image6.jpg"
    style="width:2.40972in;height:1.96528in" />\
    Terms used in trees!!

- **Root:** The topmost node of a tree.

- **Parent:** A node that has one or more child nodes.

- **Child:** A node connected below another node.

- **Leaf:** A node that has no children.

  1.  Graphs

      A graph is a data structure consisting of nodes (also known as
      vertices) and the connections between them (also known as edges).

      Commonly used to represent relationships and connections between
      different objects.

      For example, they can represent social networks, maps, and
      computer networks.

      <img src="CHAPTER4_media/media/image7.jpg"
      style="width:2.44444in;height:1.57639in" />

  2.  Hash Table

      A hash table is a fast method of storing and searching item where
      the search item is put through a hash function before being stored
      in the computer’s memory. It assigns values to specific positions
      of an array.

      <img src="CHAPTER4_media/media/image8.jpg"
      style="width:3.22222in;height:2.07639in" />

  3.  Heaps

      <span class="mark">A heap is a data structure that keeps data
      organized, with min-heaps having the smallest value on top and
      max-heaps having the largest.</span>

      <span class="mark">Heaps are commonly used in priority queues and
      scheduling systems.</span>

      <img src="CHAPTER4_media/media/image9.jpg"
      style="width:2.81944in;height:1.88194in" />

      A heap is a specialized tree-based data structure that follows a
      specific ordering rule.

<!-- -->

- **Min-Heap:** The parent node is smaller than or equal to its child
  nodes, so the smallest element is at the root.

- **Max-Heap:** The parent node is greater than or equal to its child
  nodes, so the largest element is at the root.

> [<span class="mark"><u>https://www.bosscoderacademy.com/blog/beginners-guide-to-data-structures-and-algorithms</u></span>](https://www.bosscoderacademy.com/blog/beginners-guide-to-data-structures-and-algorithms)

2.  <span class="mark">Abstract Data Types</span>

- <span class="mark">Abstract Data Type (ADT) is a conceptual model. It
  defines what a data structure does without dictating how it does it.
  By separating the logical properties from the physical implementation,
  ADTs allow for cleaner, more maintainable code.</span>

- <span class="mark">In simple terms, an ADT focuses on **what a data
  structure does rather than how it works internally**.</span>

- <span class="mark">For example, a Stack ADT defines that elements are
  added using push and removed using pop, following the LIFO principle.
  However, it does not specify whether the stack must be implemented
  using an array or a linked list.</span>

> <img src="CHAPTER4_media/media/image10.jpg"
> style="width:3.11806in;height:1.44444in" />
>
> <span class="mark">As depicted in the diagram, the following features
> of ADTs are highlighted:</span>
>
> <span class="mark">▪︎ Only the essentials are exposed, omitting
> implementation details (Abstraction).</span>
>
> <span class="mark">▪︎ Data and its related operations are bundled into
> a single unit (Encapsulation).</span>
>
> <span class="mark">▪︎ You can change the underlying implementation
> (e.g., from an Array to a Linked List) without affecting how the rest
> of the program uses the ADT (Data Independence).</span>
>
> <span class="mark">Common Examples of ADTs:</span>

- <span class="mark">Queue: A linear structure following the FIFO (First
  In, First Out) principle.</span>

  <img src="CHAPTER4_media/media/image11.jpg"
  style="width:2.30556in;height:1.22917in" />

<!-- -->

- <span class="mark">List: A sequential collection of elements</span>

  <img src="CHAPTER4_media/media/image12.jpg"
  style="width:2.55556in;height:1.49306in" />

<!-- -->

- <span class="mark">Stack: A linear structure following the LIFO (Last
  In, First Out) principle.</span>

  <img src="CHAPTER4_media/media/image13.jpg"
  style="width:2.65972in;height:1.51389in" />

  <span class="mark">Differences Between ADTs and UDTs</span>

  <img src="CHAPTER4_media/media/image14.jpg"
  style="width:5.54167in;height:2.29861in" />

<span class="mark">Advantages of Abstract Data Types (ADT)</span>

- <span class="mark">Modularity: Simplifies complex systems by breaking
  them into smaller, manageable pieces.</span>

- <span class="mark">Security & Integrity: Information hiding helps
  control access to internal data and reduces accidental
  modification.</span>

- <span class="mark">Reusability: Once defined, the interface can be
  reused across different projects regardless of the backend
  logic.</span>

<span class="mark">Disadvantages of Abstract Data Types (ADT)</span>

- <span class="mark">Performance Overhead: The layers of abstraction can
  sometimes lead to slightly higher memory or CPU usage.</span>

- <span class="mark">Initial Complexity: Designing a robust ADT requires
  more upfront planning and a steeper learning curve for
  beginners.</span>

[<span class="mark"><u>https://www.geeksforgeeks.org/dsa/abstract-data-types/</u></span>](https://www.geeksforgeeks.org/dsa/abstract-data-types/)

3.  <span class="mark">Operations such as traversing, search, insertion
    and deletion</span>

- <span class="mark">Traversing**:**</span>

  <span class="mark">Traversing a data structure means to visit the
  elements stored in it. It visits data in a systematic manner. This can
  be done with any type of data structures (e.g. array, stack, queue,
  linked list).</span>

  <span class="mark">For example, consider a list containing \[10, 20,
  30, 40\]. Traversing the list means visiting each element one by
  one.</span>

  <img src="CHAPTER4_media/media/image15.png"
  style="width:1.60425in;height:0.71531in" />
  <span class="mark">Output:</span>
  <img src="CHAPTER4_media/media/image16.png"
  style="width:0.19445in;height:0.67365in" />

<!-- -->

- <span class="mark">Searching:</span>

  <span class="mark">Searching means to find a particular element in the
  given data-structure. It is considered as successful when the required
  element is found. Searching is the operation which we can perform on
  data-structures like array, linked-list, tree, graph, etc.</span>

  <span class="mark">For example, searching for the number 30 in a
  list:</span>

  <img src="CHAPTER4_media/media/image17.png"
  style="width:1.75009in;height:1.02089in" /> <span class="mark">Output:
  Element found</span>

<!-- -->

- <span class="mark">Insertion:</span>

  Insertion is an operation used to add an element to a data structure.
  The element can be added at a specific position or according to the
  rules of the data structure. In some cases, insertion may require
  additional memory or may be limited by the capacity of the structure.

  The insertion operation has different names in certain data
  structures. In a stack, it is called Push. In a queue, it is called
  Enqueue.

  Example:

  <img src="CHAPTER4_media/media/image18.png"
  style="width:1.34035in;height:0.83338in" /> Output: \[10, 20, 30, 40\]

<!-- -->

- <span class="mark">Deletion:</span>

  Deletion is an operation used to remove an existing element from a
  data structure. The element to be removed depends on the structure and
  the operation being performed. In a stack, deletion is called Pop,
  while in a queue, it is called Dequeue.

  Example:

  <img src="CHAPTER4_media/media/image19.png"
  style="width:1.54869in;height:0.92366in" /> Output: \[10, 20, 40\]

> <span class="mark">Some other method :</span>
>
> <span class="mark">° Update</span>
>
> <span class="mark">It updates the data in the data structure. You can
> also update any specific data by giving some condition in loop like
> select approach.</span>
>
> <span class="mark">For example:</span>
>
> <img src="CHAPTER4_media/media/image20.png"
> style="width:1.60425in;height:0.84032in" /> <span class="mark">Output:
> \[10, 25, 30, 40\]</span>
>
> <span class="mark">The value at index 1 changes from 20 to 25.</span>
>
> <span class="mark">° Sort</span>
>
> <span class="mark">Sorting data in a particular order (ascending or
> descending).</span>
>
> <span class="mark">For example:</span>
>
> <img src="CHAPTER4_media/media/image21.png"
> style="width:1.38202in;height:0.87504in" /> <span class="mark">Output:
> \[1, 2, 5, 8\]</span>
>
> <span class="mark">There are different sorting algorithms, such as
> Bubble Sort, Selection Sort, Insertion Sort, Merge Sort, and Quick
> Sort. These algorithms will be explained in more detail in the chapter
> about searching and sorting.</span>
>
> [<span class="mark"><u>https://www.geeksforgeeks.org/dsa/common-operations-on-various-data-structures/</u></span>](https://www.geeksforgeeks.org/dsa/common-operations-on-various-data-structures/)

4.  <span class="mark">Q n A Time</span>

<!-- -->

1.  <span class="mark">What is the core definition of Data
    Structures?</span>

    <span class="mark">A. Methods to organize and store data in a
    database so it's secure and encrypted</span>

    <span class="mark">B. Ways to organize and store data in a computer
    so it's easy to access and manage</span>

    <span class="mark">C. Techniques to organize and store data in a
    network so it's fast to transfer and share</span>

    <span class="mark">D. Processes to organize and store data in a
    system so it's compressed and archived</span>

2.  <span class="mark">Stacks and Queues are classified as linear
    structures but with different principles. Which is correct?</span>

    <span class="mark">A. Both are FIFO - First In First Out</span>

    <span class="mark">B. Both are LIFO - Last In First Out</span>

    <span class="mark">C. Stack is LIFO - Last In First Out, Queue is
    FIFO - First In First Out</span>

    <span class="mark">D. Stack is FIFO -First In First Out, Queue is
    LIFO - Last In First Out</span>

3.  <span class="mark">Insertion in Stack and Queue has special names.
    Which is correct?</span>

    <span class="mark">A. In Stack called Enqueue, in Queue called
    Push</span>

    <span class="mark">B. In Stack called Push, in Queue called
    Enqueue</span>

    <span class="mark">C. In Stack called Pop, in Queue called
    Dequeue</span>

    <span class="mark">D. In both Stack and Queue called Merge</span>

4.  <span class="mark">What does traversing a data structure mean
    ?</span>

    <span class="mark">A. Visiting data in a systematic manner</span>

    <span class="mark">B. Adding an element, unsuccessful when structure
    is full</span>

    <span class="mark">C. Deleting an element, called Pop in Stack and
    Dequeue in Queue</span>

    <span class="mark">D. Creating concrete implementations using
    primitive types</span>

5.  <span class="mark">What is ADT (Abstract Data Types)?</span>

    <span class="mark">A. Concrete implementation creating data types
    using primitive types like int char</span>

    <span class="mark">B. Basic structure storing multiple items of same
    type in one memory block completely</span>

    <span class="mark">C. Operation visiting element stored in structure
    in systematic manner for processing</span>

    <span class="mark">D. Conceptual model defining what data structure
    does without dictating how it does</span>

6.  <span class="mark">Which operation changes the value of an existing
    element without adding or removing an element?</span>

    <span class="mark">A. Traversing</span>

    <span class="mark">B. Searching</span>

    <span class="mark">C. Insertion</span>

    <span class="mark">D. Update</span>

7.  <span class="mark">Which of the following describes a
    Min-Heap?</span>

    <span class="mark">A. The largest element is always at the
    root.</span>

    <span class="mark">B. The smallest element is always at the
    root.</span>

    <span class="mark">C. Elements are removed in the order they were
    inserted.</span>

    <span class="mark">D. Elements are stored without any ordering
    rules.</span>

    <span class="mark">Answer Key:</span>

<!-- -->

1.  <span class="mark">B</span>

2.  <span class="mark">C</span>

3.  <span class="mark">B</span>

4.  <span class="mark">A</span>

5.  <span class="mark">D</span>

6.  <span class="mark">D</span>

7.  <span class="mark">B</span>
