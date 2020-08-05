# std_vector
std_vector

## Advantages

1. Can change size dynamically.
2. Very efficient at accessing its elements and relatively efficient adding or removing elements from its end

## Disadvantages
1. Consume more memory in exchange for the ability to manage storage and grow dynamically in an efficient way
   - They may need to be reallocated in order to grow in size when new elements are inserted. This is a relatively expensive task in terms of processing time.
   - But they do not reallocate each time an element is added to the container. Instead vector containers may allocate some extra storage to accommodate for possible growth
   
2. For operations that involve inserting or removing elements at positions other than the end, they perform worse than the others, and have less consistent iterators and references than lists and forward_lists.
3.  Inserting at the end takes differential time, as sometimes there may be a need of extending the array. Removing the last element takes only constant time because no resizing happens


### Iterators

- begin() – Returns an iterator pointing to the first element in the vector
- end() – Returns an iterator pointing to the **theoretical element that follows the last element in the vector**
- rbegin() – Returns a reverse iterator pointing to the last element in the vector . It moves from last to first element
- rend() – Returns a reverse iterator pointing to the **theoretical element preceding the first element in the vector**
- cbegin() – Returns a constant iterator pointing to the first element in the vector.
- cend() – Returns a constant iterator pointing to the theoretical element that follows the last element in the vector.
- crbegin() – Returns a constant reverse iterator pointing to the last element in the vector (reverse beginning). It moves from last to first element
- crend() – Returns a constant reverse iterator pointing to the theoretical element preceding the first element in the vector (considered as reverse end)

### Functions ###
- size() – Returns the number of elements in the vector.
- max_size() – Returns the maximum number of elements that the vector can hold. Theoretical limit of the platform.
- capacity() – Maximum number of elements it could contain without having to allocate new memory. The capacity does not suppose a limit on the size of the vector. When this capacity is exhausted and more is needed, it is automatically expanded by the container 
- resize(n) – Resizes the container so that it contains ‘n’ elements.
- empty() – Returns whether the container is empty.
- shrink_to_fit() – Reduces the capacity of the container to fit its size and destroys all elements beyond the capacity.
- reserve() – Requests that the vector capacity be at least enough to contain n elements.

### Element access ###
- at(g)   –  reference to element at position ‘g’
- front() – reference to first element in the vector
- back()  – reference to last element in the vector
- data()  – Returns a direct pointer to the memory array used internally by the vector to store its owned elements.

```
int main() 
{ 
    vector<int> g1; 
    for (int i = 1; i <= 10; i++) 
        g1.push_back(i * 10); 
    cout << "\nReference operator [g] : g1[2] = " << g1[2]; 
    int* pos = g1.data(); 
    cout << "\nThe first element is " << *pos; 
    return 0; 
} 

Output:
Reference operator [g] : g1[2] = 30
The first element is 10

```

### Modifiers ###

- assign() – It assigns new value to the vector elements by replacing old ones
- push_back() – It push the elements into a vector from the back
- pop_back() – It is used to pop or remove elements from a vector from the back.
- insert() – It inserts new elements before the element at the specified position
- erase() – It is used to remove elements from a container from the specified position or range.
- swap() – It is used to swap the contents of one vector with another vector of same type. Sizes may differ.
- clear() – It is used to remove all the elements of the vector container
- emplace() – It extends the container by inserting new element at position
- emplace_back() – It is used to insert a new element into the vector container, the new element is added to the end of the vector

```
int main() 
{ 
    vector<int> v; 
  
    // fill the array with 10 five times 
    v.assign(5, 10); 
  
    cout << "The vector elements are: "; 
    for (int i = 0; i < v.size(); i++) 
        cout << v[i] << " "; 
  
    // inserts 15 to the last position 
    v.push_back(15); 
    int n = v.size(); 
    cout << "\nThe last element is: " << v[n - 1]; 
  
    // removes last element 
    v.pop_back(); 
  
    // prints the vector 
    cout << "\nThe vector elements are: "; 
    for (int i = 0; i < v.size(); i++) 
        cout << v[i] << " "; 
  
    // inserts 5 at the beginning 
    v.insert(v.begin(), 5); 
  
    cout << "\nThe first element is: " << v[0]; 
  
    // removes the first element 
    v.erase(v.begin()); 
  
    cout << "\nThe first element is: " << v[0]; 
  
    // inserts at the beginning 
    v.emplace(v.begin(), 5); 
    cout << "\nThe first element is: " << v[0]; 
  
    // Inserts 20 at the end 
    v.emplace_back(20); 
    n = v.size(); 
    cout << "\nThe last element is: " << v[n - 1]; 
  
    // erases the vector 
    v.clear(); 
    cout << "\nVector size after erase(): " << v.size(); 
  
    // Swaps v1 and v2 (commented creatingcode, just showing usage)
    v1.swap(v2); 
} 

Output:
The vector elements are: 10 10 10 10 10 
The last element is: 15
The vector elements are: 10 10 10 10 10 
The first element is: 5
The first element is: 10
The first element is: 5
The last element is: 20
Vector size after erase(): 0



```
