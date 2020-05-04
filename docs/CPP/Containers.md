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

