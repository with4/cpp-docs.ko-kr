---
title: "multimap(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/map> 헤더[STL/CLR]"
  - "<map> 헤더[STL/CLR]"
  - "multimap 클래스[STL/CLR]"
ms.assetid: 3dfe329d-a078-462a-b050-7999ce6110ad
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# multimap(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that controls a varying\-length sequence of elements that has bidirectional access.  You use the container `multimap` to manage a sequence of elements as a \(nearly\) balanced ordered tree of nodes, each storing one element.  An element consists of a key, for ordering the sequence, and a mapped value, which goes along for the ride.  
  
 In the description below, `GValue` is the same as:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 다음은 각 문자에 대한 설명입니다.  
  
 `GKey` is the same as `Key` unless the latter is a ref type, in which case it is `Key^`  
  
 `GMapped` is the same as `Mapped` unless the latter is a ref type, in which case it is `Mapped^`  
  
## 구문  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class multimap  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
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
|[multimap::const\_iterator](../dotnet/multimap-const-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[multimap::const\_reference](../dotnet/multimap-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[multimap::const\_reverse\_iterator](../dotnet/multimap-const-reverse-iterator-stl-clr.md)|The type of a constant reverse iterator for the controlled sequence.|  
|[multimap::difference\_type](../dotnet/multimap-difference-type-stl-clr.md)|The type of a \(possibly signed\) distance between two elements.|  
|[multimap::generic\_container](../dotnet/multimap-generic-container-stl-clr.md)|The type of the generic interface for the container.|  
|[multimap::generic\_iterator](../dotnet/multimap-generic-iterator-stl-clr.md)|The type of an iterator for the generic interface for the container.|  
|[multimap::generic\_reverse\_iterator](../dotnet/multimap-generic-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the generic interface for the container.|  
|[multimap::generic\_value](../dotnet/multimap-generic-value-stl-clr.md)|The type of an element for the generic interface for the container.|  
|[multimap::iterator](../dotnet/multimap-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md)|The ordering delegate for two keys.|  
|[multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md)|정렬 키의 형식입니다.|  
|[multimap::mapped\_type](../dotnet/multimap-mapped-type-stl-clr.md)|The type of the mapped value associated with each key.|  
|[multimap::reference](../dotnet/multimap-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[multimap::reverse\_iterator](../dotnet/multimap-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the controlled sequence.|  
|[multimap::size\_type](../dotnet/multimap-size-type-stl-clr.md)|The type of a \(non\-negative\) distance between two elements.|  
|[multimap::value\_compare](../dotnet/multimap-value-compare-stl-clr.md)|The ordering delegate for two element values.|  
|[multimap::value\_type](../dotnet/multimap-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|Member Function|설명|  
|---------------------|--------|  
|[multimap::begin](../dotnet/multimap-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[multimap::clear](../dotnet/multimap-clear-stl-clr.md)|Removes all elements.|  
|[multimap::count](../dotnet/multimap-count-stl-clr.md)|Counts elements matching a specified key.|  
|[multimap::empty](../dotnet/multimap-empty-stl-clr.md)|Tests whether no elements are present.|  
|[multimap::end](../dotnet/multimap-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[multimap::equal\_range](../dotnet/multimap-equal-range-stl-clr.md)|Finds range that matches a specified key.|  
|[multimap::erase](../dotnet/multimap-erase-stl-clr.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[multimap::find](../dotnet/multimap-find-stl-clr.md)|지정된 키와 일치하는 요소를 찾습니다.|  
|[multimap::insert](../dotnet/multimap-insert-stl-clr.md)|Adds elements.|  
|[multimap::key\_comp](../dotnet/multimap-key-comp-stl-clr.md)|Copies the ordering delegate for two keys.|  
|[multimap::lower\_bound](../dotnet/multimap-lower-bound-stl-clr.md)|Finds beginning of range that matches a specified key.|  
|[multimap::make\_value](../dotnet/multimap-make-value-stl-clr.md)|Constructs a value object.|  
|[multimap::multimap](../dotnet/multimap-multimap-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[multimap::rbegin](../dotnet/multimap-rbegin-stl-clr.md)|역방향 제어되는 시퀀스의 시작을 지정합니다.|  
|[multimap::rend](../dotnet/multimap-rend-stl-clr.md)|역방향 제어되는 시퀀스의 끝을 지정합니다.|  
|[multimap::size](../dotnet/multimap-size-stl-clr.md)|요소의 수를 셉니다.|  
|[multimap::swap](../dotnet/multimap-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
|[multimap::to\_array](../dotnet/multimap-to-array-stl-clr.md)|Copies the controlled sequence to a new array.|  
|[multimap::upper\_bound](../dotnet/multimap-upper-bound-stl-clr.md)|Finds end of range that matches a specified key.|  
|[multimap::value\_comp](../dotnet/multimap-value-comp-stl-clr.md)|Copies the ordering delegate for two element values.|  
  
|연산자|설명|  
|---------|--------|  
|[multimap::operator\=](../dotnet/multimap-operator-assign-stl-clr.md)|Replaces the controlled sequence.|  
|[operator\!\= \(multimap\)](../dotnet/operator-inequality-multimap-stl-clr.md)|Determines if a `multimap` object is not equal to another `multimap` object.|  
|[operator\< \(multimap\)](../dotnet/operator-less-than-multimap-stl-clr.md)|Determines if a `multimap` object is less than another `multimap` object.|  
|[operator\<\= \(multimap\)](../dotnet/operator-less-or-equal-multimap-stl-clr.md)|Determines if a `multimap` object is less than or equal to another `multimap` object.|  
|[operator\=\= \(multimap\)](../dotnet/operator-equality-multimap-stl-lr.md)|Determines if a `multimap` object is equal to another `multimap` object.|  
|[operator\> \(multimap\)](../dotnet/operator-greater-than-multimap-stl-clr.md)|Determines if a `multimap` object is greater than another `multimap` object.|  
|[operator\>\= \(multimap\)](../dotnet/operator-greater-or-equal-multimap-stl-clr.md)|Determines if a `multimap` object is greater than or equal to another `multimap` object.|  
  
## 인터페이스  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:System.ICloneable>|Duplicate an object.|  
|<xref:System.Collections.IEnumerable>|Sequence through elements.|  
|<xref:System.Collections.ICollection>|Maintain group of elements.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Sequence through typed elements.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintain group of typed elements.|  
|ITree\<Key, Value\>|Maintain generic container.|  
  
## 설명  
 The object allocates and frees storage for the sequence it controls as individual nodes.  It inserts elements into a \(nearly\) balanced tree that it keeps ordered by altering the links between nodes, never by copying the contents of one node to another.  That means you can insert and remove elements freely without disturbing remaining elements.  
  
 The object orders the sequence it controls by calling a stored delegate object of type [multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md).  You can specify the stored delegate object when you construct the multimap; if you specify no delegate object, the default is the comparison `operator<(key_type, key_type)`.  You access this stored object by calling the member function [multimap::key\_comp](../dotnet/multimap-key-comp-stl-clr.md)`()`.  
  
 Such a delegate object must impose a strict weak ordering on keys of type [multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md).  That means, for any two keys `X` and `Y`:  
  
 `key_comp()(X, Y)` returns the same Boolean result on every call.  
  
 If `key_comp()(X, Y)` is true, then `key_comp()(Y, X)` must be false.  
  
 If `key_comp()(X, Y)` is true, then `X` is said to be ordered before `Y`.  
  
 If `!key_comp()(X, Y) && !key_comp()(Y, X)` is true, then `X` and `Y` are said to have equivalent ordering.  
  
 For any element `X` that precedes `Y` in the controlled sequence, `key_comp()(Y, X)` is false. \(For the default delegate object, keys never decrease in value.\) Unlike template class [map](../dotnet/map-stl-clr.md), an object of template class `multimap` does not require that keys for all elements are unique. \(Two or more keys can have equivalent ordering.\)  
  
 Each element contains a separate key and a mapped value.  The sequence is represented in a way that permits lookup, insertion, and removal of an arbitrary element with a number of operations proportional to the logarithm of the number of elements in the sequence \(logarithmic time\).  Moreover, inserting an element invalidates no iterators, and removing an element invalidates only those iterators which point at the removed element.  
  
 A multimap supports bidirectional iterators, which means you can step to adjacent elements given an iterator that designates an element in the controlled sequence.  A special head node corresponds to the iterator returned by [multimap::end](../dotnet/multimap-end-stl-clr.md)`()`.  You can decrement this iterator to reach the last element in the controlled sequence, if present.  You can increment a multimap iterator to reach the head node, and it will then compare equal to `end()`.  But you cannot dereference the iterator returned by `end()`.  
  
 Note that you cannot refer to a multimap element directly given its numerical position \-\- that requires a random\-access iterator.  
  
 A multimap iterator stores a handle to its associated multimap node, which in turn stores a handle to its associated container.  You can use iterators only with their associated container objects.  A multimap iterator remains valid so long as its associated multimap node is associated with some multimap.  Moreover, a valid iterator is dereferencable \-\- you can use it to access or alter the element value it designates \-\- so long as it is not equal to `end()`.  
  
 Erasing or removing an element calls the destructor for its stored value.  Destroying the container erases all elements.  Thus, a container whose element type is a ref class ensures that no elements outlive the container.  Note, however, that a container of handles does `not` destroy its elements.  
  
## 요구 사항  
 **Header:** \<cliext\/map\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)