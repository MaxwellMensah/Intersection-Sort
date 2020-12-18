# Intersection-Sort

Consider you have 10 cards out of a deck of cards in your hand. And they are sorted, or arranged in the ascending order of their numbers.

If I give you another card, and ask you to insert the card in just the right position, so that the cards in your hand are still sorted. What will you do?

Well, you will have to go through each card from the starting or the back and find the right position for the new card, comparing it's value with each card. Once you find the right position, you will insert the card there.

Similarly, if more new cards are provided to you, you can easily repeat the same process and insert the new cards and keep the cards sorted too.

This is exactly how insertion sort works. It starts from the index 1(not 0), and each index starting from index 1 is like a new card, that you have to place at the right position in the sorted subarray on the left.


How Insertion Sort Works?
Following are the steps involved in insertion sort:

1. We start by making the second element of the given array, i.e. element at index 1, the key. The key element here is the new card that we need to add to our existing sorted set of cards(remember the example with cards above).
2. We compare the key element with the element(s) before it, in this case, element at index 0:
    - If the key element is less than the first element, we insert the key element before the first element.
    - If the key element is greater than the first element, then we insert it after the first element.
3. Then, we make the third element of the array as key and will compare it with elements to it's left and insert it at the right position.
And we go on repeating this, until the array is sorted.<br/><br/>

As you can see in the diagram above, after picking a key, we start iterating over the elements to the left of the key.

We continue to move towards left if the elements are greater than the key element and stop when we find the element which is less than the key element.

And, insert the key element after the element which is less than the key element.
<br/>

# Implementing Insertion Sort Algorithm.

//member functions declaration <br/><br/>
void insertionSort(int arr[], int length); <br/>
void printArray(int array[], int size);<br/>
 
// main function<br/>
int main() <br/>
{               <br/>      <br/><br/>
	int array[5] = {5, 1, 6, 2, 4, 3};<br/>
	// calling insertion sort function to sort the array<br/>
	insertionSort(array, 6);   <br/>
	return 0;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;}<br/>
 
void insertionSort(int arr[], int length) <br/>
{<br/>
	int i, j, key;<br/>
	for (i = 1; i < length; i++) <br/>
	{<br/>
		j = i;<br/>
 		while (j > 0 && arr[j - 1] > arr[j]) <br/>
 	&nbsp;&nbsp;&nbsp;&nbsp;	{
 			key = arr[j];<br/>
 			arr[j] = arr[j - 1];<br/>
 			arr[j - 1] = key;<br/>
 			j--;<br/>
 		&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>
	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>
	cout << "Sorted Array: ";<br/>
	// print the sorted array<br/>
	printArray(arr, length);<br/>
&nbsp;&nbsp;&nbsp;&nbsp;}<br/>
<br/>
// function to print the given array <br/>
void printArray(int array[], int size)<br/>
{ <br/>
 &nbsp;&nbsp;&nbsp;	int j;<br/>
 for (j = 0; j < size; j++)<br/>

&nbsp;&nbsp;	{<br/>
 		cout <<" "<< array[j];<br/>
 	
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>
 	cout << endl;<br/>
}<br/>
