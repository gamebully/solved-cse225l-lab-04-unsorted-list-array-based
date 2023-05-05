Download Link: https://assignmentchef.com/product/solved-cse225l-lab-04-unsorted-list-array-based
<br>



<strong> </strong>

In today’s lab we will design and implement the List ADT where the items in the list are unsorted.

<table width="0">

 <tbody>

  <tr>

   <td width="338"><strong>unsortedtype.h </strong> #ifndef UNSORTEDTYPE_H_INCLUDED#define UNSORTEDTYPE_H_INCLUDED const int MAX_ITEMS = 5; template &lt;class ItemType&gt; class UnsortedType{     public :UnsortedType();         void MakeEmpty();         bool IsFull();         int LengthIs();void InsertItem(ItemType);         void DeleteItem(ItemType);         void RetrieveItem(ItemType&amp;, bool&amp;);         void ResetList();void GetNextItem(ItemType&amp;);     private:int length;ItemType info[MAX_ITEMS];         int currentPos;};#endif // UNSORTEDTYPE_H_INCLUDED <strong>unsortedtype.cpp </strong> #include “UnsortedType.h” template &lt;class ItemType&gt;UnsortedType&lt;ItemType&gt;::UnsortedType(){length = 0;     currentPos = -1;}template &lt;class ItemType&gt;void UnsortedType&lt;ItemType&gt;::MakeEmpty(){length = 0;}template &lt;class ItemType&gt;bool UnsortedType&lt;ItemType&gt;::IsFull(){return (length == MAX_ITEMS);}template &lt;class ItemType&gt;int UnsortedType&lt;ItemType&gt;::LengthIs(){return length;}template &lt;class ItemType&gt;void UnsortedType&lt;ItemType&gt;::ResetList(){currentPos = -1;}template &lt;class ItemType&gt;voidUnsortedType&lt;ItemType&gt;::GetNextItem(ItemType&amp; item){currentPos++;item = info [currentPos] ;}</td>

   <td width="374">template &lt;class ItemType&gt;voidUnsortedType&lt;ItemType&gt;::RetrieveItem(ItemType&amp; item, bool &amp;found){int location = 0;bool moreToSearch = (location &lt; length);     found = false;while (moreToSearch &amp;&amp; !found){if(item == info[location]){found = true;item = info[location];}         else         {location++;moreToSearch = (location &lt; length);}}}template &lt;class ItemType&gt;void UnsortedType&lt;ItemType&gt;::InsertItem(ItemType item){info[length] = item;     length++;}template &lt;class ItemType&gt;void UnsortedType&lt;ItemType&gt;::DeleteItem(ItemType item){int location = 0;while (item != info[location])         location++;info[location] = info[length – 1];     length–;}</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong>                 </strong>

Generate the <strong>driver file (main.cpp) </strong>where you perform the following tasks. Note that you cannot make any change to the header file or the source file.

<table width="0">

 <tbody>

  <tr>

   <td width="362"><strong>Operation to Be Tested and Description of Action </strong></td>

   <td width="174"><strong>Input Values </strong></td>

   <td width="166"><strong>Expected Output </strong></td>

  </tr>

  <tr>

   <td width="362">        •     Create a list of integers</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Insert four items</td>

   <td width="174">5   7   6   9</td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Print the list</td>

   <td width="174"> </td>

   <td width="166">5 7 6 9</td>

  </tr>

  <tr>

   <td width="362">        •     Print the length of the list</td>

   <td width="174"> </td>

   <td width="166">4</td>

  </tr>

  <tr>

   <td width="362">        •     Insert one item</td>

   <td width="174">1</td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Print the list</td>

   <td width="174"> </td>

   <td width="166">5 7 6 9 1</td>

  </tr>

  <tr>

   <td width="362">        •    Retrieve 4 and print whether found or not</td>

   <td width="174"> </td>

   <td width="166">Item is not found</td>

  </tr>

  <tr>

   <td width="362">        •    Retrieve 5 and print whether found or not</td>

   <td width="174"> </td>

   <td width="166">Item is found</td>

  </tr>

  <tr>

   <td width="362">        •    Retrieve 9 and print whether found or not</td>

   <td width="174"> </td>

   <td width="166">Item is found</td>

  </tr>

  <tr>

   <td width="362">        •    Retrieve 10 and print whether found or not</td>

   <td width="174"> </td>

   <td width="166">Item is not found</td>

  </tr>

  <tr>

   <td width="362">        •     Print if the list is full or not</td>

   <td width="174"> </td>

   <td width="166">List is full</td>

  </tr>

  <tr>

   <td width="362">        •     Delete 5</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Print if the list is full or not</td>

   <td width="174"> </td>

   <td width="166">List is not full</td>

  </tr>

  <tr>

   <td width="362">        •     Delete 1</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Print the list</td>

   <td width="174"> </td>

   <td width="166">7 6 9</td>

  </tr>

  <tr>

   <td width="362">        •     Delete 6</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Print the list</td>

   <td width="174"> </td>

   <td width="166">7 9</td>

  </tr>

  <tr>

   <td width="362">•     Write a class studentInfo that represents a student record. It must have variables to store the student ID, student’s name and student’s CGPA. It also must have a function to print all the values. You will also need to overload a few operators.</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Create a list of objects of class studentInfo.</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •    Insert 5 student records</td>

   <td width="174">15234   Jon   2.613732   Tyrion   3.913569   Sandor   1.215467   Ramsey 2   3.116285   Arya   3.1</td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">        •     Delete the record with ID 15467</td>

   <td width="174"> </td>

   <td width="166"> </td>

  </tr>

  <tr>

   <td width="362">•     Retrieve the record with ID 13569 and print whether found or not along with the entire record</td>

   <td width="174"> </td>

   <td width="166">Item is found13569, Sandor, 1.2</td>

  </tr>

  <tr>

   <td width="362">        •     Print the list</td>

   <td width="174"> </td>

   <td width="166">15234, Jon, 2..613732, Tyrion, 3.913569, Sandor, 1.216285, Arya, 3.1</td>

  </tr>

 </tbody>

</table>


