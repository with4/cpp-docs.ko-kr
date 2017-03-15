---
title: "hash_map(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/hash_map> 헤더[STL/CLR]"
  - "<hash_map> 헤더[STL/CLR]"
  - "hash_map 클래스[STL/CLR]"
ms.assetid: c3cfc69b-04c6-42ae-a30e-0eda953fe883
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# hash_map(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that controls a varying\-length sequence of elements that has bidirectional access.  You use the container `hash_map` to manage a sequence of elements as a hash table, each table entry storing a bidirectional linked list of nodes, and each node storing one element.  An element consists of a key, for ordering the sequence, and a mapped value, which goes along for the ride.  
  
 In the description below, `GValue` is the same as:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 다음은 각 문자에 대한 설명입니다.  
  
 `GKey` is the same as `Key` unless the latter is a ref type, in which case it is `Key^`  
  
 `GMapped` is the same as `Mapped` unless the latter is a ref type, in which case it is `Mapped^`  
  
## 구문  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class hash_map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### 매개 변수  
 Key  
 제어되는 시퀀스에 있는 요소의 키 구성 요소 형식입니다.  
  
 Mapped  
 The type of the additional component of an element in the controlled sequence.  
  
## 멤버  
  
|Type Definition|설명|  
|---------------------|--------|  
|[hash\_map::const\_iterator](../dotnet/hash-map-const-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[hash\_map::const\_reference](../dotnet/hash-map-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[hash\_map::const\_reverse\_iterator](../dotnet/hash-map-const-reverse-iterator-stl-clr.md)|The type of a constant reverse iterator for the controlled sequence.|  
|[hash\_map::difference\_type](../dotnet/hash-map-difference-type-stl-clr.md)|The type of a \(possibly signed\) distance between two elements.|  
|[hash\_map::generic\_container](../dotnet/hash-map-generic-container-stl-clr.md)|The type of the generic interface for the container.|  
|[hash\_map::generic\_iterator](../dotnet/hash-map-generic-iterator-stl-clr.md)|The type of an iterator for the generic interface for the container.|  
|[hash\_map::generic\_reverse\_iterator](../dotnet/hash-map-generic-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the generic interface for the container.|  
|[hash\_map::generic\_value](../dotnet/hash-map-generic-value-stl-clr.md)|The type of an element for the generic interface for the container.|  
|[hash\_map::hasher](../dotnet/hash-map-hasher-stl-clr.md)|The hashing delegate for a key.|  
|[hash\_map::iterator](../dotnet/hash-map-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[hash\_map::key\_compare](../dotnet/hash-map-key-compare-stl-clr.md)|The ordering delegate for two keys.|  
|[hash\_map::key\_type](../dotnet/hash-map-key-type-stl-clr.md)|정렬 키의 형식입니다.|  
|[hash\_map::mapped\_type](../dotnet/hash-map-mapped-type-stl-clr.md)|The type of the mapped value associated with each key.|  
|[hash\_map::reference](../dotnet/hash-map-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[hash\_map::reverse\_iterator](../dotnet/hash-map-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the controlled sequence.|  
|[hash\_map::size\_type](../dotnet/hash-map-size-type-stl-clr.md)|The type of a \(non\-negative\) distance between two elements.|  
|[hash\_map::value\_compare](../dotnet/hash-map-value-compare-stl-clr.md)|The ordering delegate for two element values.|  
|[hash\_map::value\_type](../dotnet/hash-map-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|Member Function|설명|  
|---------------------|--------|  
|[hash\_map::begin](../dotnet/hash-map-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[hash\_map::bucket\_count](../dotnet/hash-map-bucket-count-stl-clr.md)|Counts the number of buckets.|  
|[hash\_map::clear](../dotnet/hash-map-clear-stl-clr.md)|Removes all elements.|  
|[hash\_map::count](../dotnet/hash-map-count-stl-clr.md)|Counts elements matching a specified key.|  
|[hash\_map::empty](../dotnet/hash-map-empty-stl-clr.md)|Tests whether no elements are present.|  
|[hash\_map::end](../dotnet/hash-map-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[hash\_map::equal\_range](../dotnet/hash-map-equal-range-stl-clr.md)|Finds range that matches a specified key.|  
|[hash\_map::erase](../dotnet/hash-map-erase-stl-clr.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[hash\_map::find](../dotnet/hash-map-find-stl-clr.md)|지정된 키와 일치하는 요소를 찾습니다.|  
|[hash\_map::hash\_delegate](../dotnet/hash-map-hash-delegate-stl-clr.md)|Copies the hashing delegate for a key.|  
|[hash\_map::hash\_map](../dotnet/hash-map-hash-map-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[hash\_map::insert](../dotnet/hash-map-insert-stl-clr.md)|Adds elements.|  
|[hash\_map::key\_comp](../dotnet/hash-map-key-comp-stl-clr.md)|Copies the ordering delegate for two keys.|  
|[hash\_map::load\_factor](../dotnet/hash-map-load-factor-stl-clr.md)|Counts the average elements per bucket.|  
|[hash\_map::lower\_bound](../dotnet/hash-map-lower-bound-stl-clr.md)|Finds beginning of range that matches a specified key.|  
|[hash\_map::make\_value](../dotnet/hash-map-make-value-stl-clr.md)|Constructs a value object.|  
|[hash\_map::max\_load\_factor](../dotnet/hash-map-max-load-factor-stl-clr.md)|Gets or sets the maximum elements per bucket.|  
|[hash\_map::rbegin](../dotnet/hash-map-rbegin-stl-clr.md)|역방향 제어되는 시퀀스의 시작을 지정합니다.|  
|[hash\_map::rehash](../dotnet/hash-map-rehash-stl-clr.md)|해시 테이블을 다시 빌드합니다.|  
|[hash\_map::rend](../dotnet/hash-map-rend-stl-clr.md)|역방향 제어되는 시퀀스의 끝을 지정합니다.|  
|[hash\_map::size](../dotnet/hash-map-size-stl-clr.md)|요소의 수를 셉니다.|  
|[hash\_map::swap](../dotnet/hash-map-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
|[hash\_map::to\_array](../dotnet/hash-map-to-array-stl-clr.md)|Copies the controlled sequence to a new array.|  
|[hash\_map::upper\_bound](../dotnet/hash-map-upper-bound-stl-clr.md)|Finds end of range that matches a specified key.|  
|[hash\_map::value\_comp](../dotnet/hash-map-value-comp-stl-clr.md)|Copies the ordering delegate for two element values.|  
  
|연산자|설명|  
|---------|--------|  
|[hash\_map::operator\=](../dotnet/hash-map-operator-assign-stl-clr.md)|Replaces the controlled sequence.|  
|[hash\_map::operator](../dotnet/hash-map-operator-stl-clr.md)|Maps a key to its associated mapped value.|  
  
## 인터페이스  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:System.ICloneable>|Duplicate an object.|  
|<xref:System.Collections.IEnumerable>|Sequence through elements.|  
|<xref:System.Collections.ICollection>|Maintain group of elements.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Sequence through typed elements.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintain group of typed elements.|  
|<xref:System.Collections.Generic.IDictionary%602>|Maintain group of {key, value} pairs.|  
|IHash\<Key, Value\>|Maintain generic container.|  
  
## 설명  
 The object allocates and frees storage for the sequence it controls as individual nodes in a bidirectional linked list.  To speed access, the object also maintains a varying\-length array of pointers into the list \(the hash table\), effectively managing the whole list as a sequence of sublists, or buckets.  It inserts elements into a bucket that it keeps ordered by altering the links between nodes, never by copying the contents of one node to another.  That means you can insert and remove elements freely without disturbing remaining elements.  
  
 The object orders each bucket it controls by calling a stored delegate object of type [hash\_set::key\_compare](../dotnet/hash-set-key-compare-stl-clr.md).  You can specify the stored delegate object when you construct the hash\_set; if you specify no delegate object, the default is the comparison `operator<=(key_type, key_type)`.  
  
 You access the stored delegate object by calling the member function [hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)`()`.  Such a delegate object must define equivalent ordering between keys of type [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md).  That means, for any two keys `X` and `Y`:  
  
 `key_comp()(X, Y)` returns the same Boolean result on every call.  
  
 If `key_comp()(X, Y) && key_comp()(Y, X)` is true, then `X` and `Y` are said to have equivalent ordering.  
  
 Any ordering rule that behaves like `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` or `operator==(key_type, key_type)` defines eqivalent ordering.  
  
 Note that the container ensures only that elements whose keys have equivalent ordering \(and which hash to the same integer value\) are adjacent within a bucket.  Unlike template class [hash\_multimap](../dotnet/hash-multimap-stl-clr.md), an object of template class `hash_map` ensures that keys for all elements are unique. \(No two keys have equivalent ordering.\)  
  
 The object determines which bucket should contain a given ordering key by calling a stored delegate object of type [hash\_set::hasher](../dotnet/hash-set-hasher-stl-clr.md).  You access this stored object by calling the member function [hash\_set::hash\_delegate](../dotnet/hash-set-hash-delegate-stl-clr.md)`()` to obtain an integer value that depends on the key value.  You can specify the stored delegate object when you construct the hash\_set; if you specify no delegate object, the default is the function `System::Object::hash_value(key_type)`.  That means, for any keys `X` and `Y`:  
  
 `hash_delegate()(X)` returns the same integer result on every call.  
  
 If `X` and `Y` have equivalent ordering, then `hash_delegate()(X)` should return the same integer result as `hash_delegate()(Y)`.  
  
 Each element contains a separate key and a mapped value.  The sequence is represented in a way that permits lookup, insertion, and removal of an arbitrary element with a number of operations that is independent of the number of elements in the sequence \(constant time\) \-\- at least in the best of cases.  Moreover, inserting an element invalidates no iterators, and removing an element invalidates only those iterators which point at the removed element.  
  
 If hashed values are not uniformly distributed, however, a hash table can degenerate.  In the extreme \-\- for a hash function that always returns the same value \-\- lookup, insertion, and removal are proportional to the number of elements in the sequence \(linear time\).  The container endeavors to choose a reasonable hash function, mean bucket size, and hash\-table size \(total number of buckets\), but you can override any or all of these choices.  See, for example, the functions [hash\_set::max\_load\_factor](../dotnet/hash-set-max-load-factor-stl-clr.md) and [hash\_set::rehash](../dotnet/hash-set-rehash-stl-clr.md).  
  
 A hash\_map supports bidirectional iterators, which means you can step to adjacent elements given an iterator that designates an element in the controlled sequence.  A special head node corresponds to the iterator returned by [hash\_map::end](../dotnet/hash-map-end-stl-clr.md)`()`.  You can decrement this iterator to reach the last element in the controlled sequence, if present.  You can increment a hash\_map iterator to reach the head node, and it will then compare equal to `end()`.  But you cannot dereference the iterator returned by `end()`.  
  
 Note that you cannot refer to a hash\_map element directly given its numerical position \-\- that requires a random\-access iterator.  
  
 A hash\_map iterator stores a handle to its associated hash\_map node, which in turn stores a handle to its associated container.  You can use iterators only with their associated container objects.  A hash\_map iterator remains valid so long as its associated hash\_map node is associated with some hash\_map.  Moreover, a valid iterator is dereferencable \-\- you can use it to access or alter the element value it designates \-\- so long as it is not equal to `end()`.  
  
 Erasing or removing an element calls the destructor for its stored value.  Destroying the container erases all elements.  Thus, a container whose element type is a ref class ensures that no elements outlive the container.  Note, however, that a container of handles does `not` destroy its elements.  
  
## 요구 사항  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)