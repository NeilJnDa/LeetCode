> A container is a holder object that stores a collection of other objects (its elements). They are implemented as **class templates**, which allows a great flexibility in the types supported as elements.

There are four kinds of containers:

- Sequence containers
  - array
  - vector
  - deque
  - forward_list
  - list

- Container adapters
  - stack
  - queue
  - priority_queue
- Associative containers
  - set
  - multiset
  - map
  - multimap

- Unordered associative containers
  - unordered_set
  - unordered_multiset
  - unordered_map
  - unordered_multimap

---



## Sequence Containers

---



## Container adapters

---

### priority_queue

Priority Queues are designed such that its first element is always the greatest one which is similar to a maximum *heap*. Elements can be inserted at any moment, and only the max heap element can be retrieved. Also, minimum heap can be achieved by customize the comparing method.

> Priority queues are implemented as *container adapters*, which are classes that use an encapsulated object of a specific container class as its *underlying container*, providing a specific set of member functions to access its elements. Elements are *popped* from the ***"back"*** of the specific container, which is known as the *top* of the priority queue.

#### Construct

**Maximum heap** ,`vector<T>` and `less<T>` by default.

```c++
#include<queue>		 //std::priority_queue
#include<functional> //std::greater
using namespace std;
int nums[] = {1,2,3,4};
priority_queue<int> first;
priority_queue<int> second(nums, nums+4);
priority_queue<int, vector<int>, less<int> > third;
```

> For ease of memorizing, `less<T>` could be seen as the value of child nodes are getting less.

If you want to create a **minimum heap**:

```c++
priority_queue<int, vector<int>, greater<int> > min_heap;
```

If you want to custom comparison method:

```c++
class cmp_greater{
  bool operator(const int a, const int b){
      return a > b;
      //greaater is '>' of course.
  }  
};
class cmp_less{
  bool operator(const int a, const int b){
      return a < b;
  }  
};

priority_queue<int, vector<int>, cmp_greater> max_heap_c;
priority_queue<int, vector<int>, cmp_less> min_heap_c;
```

For example, it is rather handy when comparing two nodes in linked lists:

```c++
struct ListNode {
   int val;
   ListNode *next;
};
class cmp_greater_node{
   bool operator()(const ListNode* a, const ListNode* b){
        return a->val > b->val;
   }
};
//Node with smallest value will at the top of the heap
priority_queue<ListNode*, vector<ListNode*>, cmp_greater_node) min_heap_node;
```

#### Push or Emplace

```c++
priority_queue<int> pq;
int a = 10;
pq.push(a);
pq.emplace(a); //No temp object; C++11
```

#### Pop

```c++
pq.pop();
```

#### Top

Return void

```c++
pq.top();
```

#### Property

```
pq.size(); //return the number of elements
pq.empty(); //return bool value if it's empty
```

#### Traverse

No traversal method available. It can be only achieved by `pop()` continuously.

## Associative containers

---



## Unordered associative containers



### unordered_map

Based on hash table, unordered_map allows for fast retrieval of **values** by their **keys**. It is usually used in search occasions to achieve **constant time complexity**.

Every key in the container is unique. Elements are unordered.

#### Construct

```c++
#include<unordered_map>
using namespace std;
unorder_map<string, int> ump;
unorder_map<string, int> second(ump);
unorder_map<string, char> third = second;
```

#### Insert

```c++
ump["cat"] = 3;//It will create a new pair if there is no "cat"
ump.insert(make_pair("dog", 4));
ump.insert(pair<string, int>("pig", 5));
ump.emplace(make_pair("fish", 6));//No temporary variable
```

#### Access

- find() : returns an iterator.
- at() : If key does not match the key of any element in the container, the function throws an out_of_range exception.
- count() : **only** returns the number of elements.
- operator[] : this method will **create a new pair** if there is no this key.

```c++
//find(k)
unorder_map<string, int>::iterator it;
it = ump.find("cat");
if(it != ump.end())//if no key named "cat", find() will return ump.end()
	cout<<it->first<<' '<<it->second<<endl;//cat 3

//at(k)
ump.at("cat") += 5;
ump.at("water") = 1;//Exception

//count(k)
string name = "dog";
if(ump.count(name) > 0)
    cout<<"It has "<<name<<endl;

//[k]
cout<<ump["cat"]<<endl;//3
cout<<ump["water"]<<endl;//0	
//UNSAFE: "water" dose not exist in ump, but it is created and initialized.
```

#### Erase

```c++
ump.erase(ump.begin());
ump.erase("dog");
ump.erase(ump.find("fish"));
ump.clear();//Erase all
```

#### Traverse

The elements in unordered_map are unordered, the order of traversal is generally not  the same as insertion.

```c++
unorder_map<string, int>::iterator it;
for(it = ump.begin(); it != ump.end(); it++){
    ···
}
```

#### Property

```
ump.size();//returns the number of pairs
ump.emtpy);//returns a bool value indicating whether it is empty
```

