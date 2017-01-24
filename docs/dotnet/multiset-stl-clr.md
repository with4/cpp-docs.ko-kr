---
title: "multiset(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/set> 헤더[STL/CLR]"
  - "<set> 헤더[STL/CLR]"
  - "multiset 클래스[STL/CLR]"
ms.assetid: 7c46e2b4-cd88-49b7-a9e6-63ad5ae7feb5
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that controls a varying\-length sequence of elements that has bidirectional access.  You use the container `multiset` to manage a sequence of elements as a \(nearly\) balanced ordered tree of nodes, each storing one element.  
  
 In the description below, `GValue` is the same as `GKey`, which in turn is the same as `Key` unless the latter is a ref type, in which case it is `Key^`.  
  
## 구문  
  
```  
template<typename Key>  
    ref class multiset  
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
  
## 멤버  
  
|Type Definition|설명|  
|---------------------|--------|  
|[multiset::const\_iterator](../dotnet/multiset-const-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[multiset::const\_reference](../dotnet/multiset-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[multiset::const\_reverse\_iterator](../dotnet/multiset-const-reverse-iterator-stl-clr.md)|The type of a constant reverse iterator for the controlled sequence.|  
|[multiset::difference\_type](../dotnet/multiset-difference-type-stl-clr.md)|The type of a \(possibly signed\) distance between two elements.|  
|[multiset::generic\_container](../dotnet/multiset-generic-container-stl-clr.md)|The type of the generic interface for the container.|  
|[multiset::generic\_iterator](../dotnet/multiset-generic-iterator-stl-clr.md)|The type of an iterator for the generic interface for the container.|  
|[multiset::generic\_reverse\_iterator](../dotnet/multiset-generic-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the generic interface for the container.|  
|[multiset::generic\_value](../dotnet/multiset-generic-value-stl-clr.md)|The type of an element for the generic interface for the container.|  
|[multiset::iterator](../dotnet/multiset-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md)|The ordering delegate for two keys.|  
|[multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md)|정렬 키의 형식입니다.|  
|[multiset::reference](../dotnet/multiset-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[multiset::reverse\_iterator](../dotnet/multiset-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the controlled sequence.|  
|[multiset::size\_type](../dotnet/multiset-size-type-stl-clr.md)|The type of a \(non\-negative\) distance between two elements.|  
|[multiset::value\_compare](../dotnet/multiset-value-compare-stl-clr.md)|The ordering delegate for two element values.|  
|[multiset::value\_type](../dotnet/multiset-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|Member Function|설명|  
|---------------------|--------|  
|[multiset::begin](../dotnet/multiset-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[multiset::clear](../dotnet/multiset-clear-stl-clr.md)|Removes all elements.|  
|[multiset::count](../dotnet/multiset-count-stl-clr.md)|Counts elements matching a specified key.|  
|[multiset::empty](../dotnet/multiset-empty-stl-clr.md)|Tests whether no elements are present.|  
|[multiset::end](../dotnet/multiset-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[multiset::equal\_range](../dotnet/multiset-equal-range-stl-clr.md)|Finds range that matches a specified key.|  
|[multiset::erase](../dotnet/multiset-erase-stl-clr.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[multiset::find](../dotnet/multiset-find-stl-clr.md)|지정된 키와 일치하는 요소를 찾습니다.|  
|[multiset::insert](../dotnet/multiset-insert-stl-clr.md)|Adds elements.|  
|[multiset::key\_comp](../dotnet/multiset-key-comp-stl-clr.md)|Copies the ordering delegate for two keys.|  
|[multiset::lower\_bound](../dotnet/multiset-lower-bound-stl-clr.md)|Finds beginning of range that matches a specified key.|  
|[multiset::make\_value](../dotnet/multiset-make-value-stl-clr.md)|Constructs a value object.|  
|[multiset::multiset](../dotnet/multiset-multiset-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[multiset::rbegin](../dotnet/multiset-rbegin-stl-clr.md)|역방향 제어되는 시퀀스의 시작을 지정합니다.|  
|[multiset::rend](../dotnet/multiset-rend-stl-clr.md)|역방향 제어되는 시퀀스의 끝을 지정합니다.|  
|[multiset::size](../dotnet/multiset-size-stl-clr.md)|요소의 수를 셉니다.|  
|[multiset::swap](../dotnet/multiset-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
|[multiset::to\_array](../dotnet/multiset-to-array-stl-clr.md)|Copies the controlled sequence to a new array.|  
|[multiset::upper\_bound](../dotnet/multiset-upper-bound-stl-clr.md)|Finds end of range that matches a specified key.|  
|[multiset::value\_comp](../dotnet/multiset-value-comp-stl-clr.md)|Copies the ordering delegate for two element values.|  
  
|연산자|설명|  
|---------|--------|  
|[multiset::operator\=](../dotnet/multiset-operator-assign-stl-clr.md)|Replaces the controlled sequence.|  
|[operator\!\= \(multiset\)](../dotnet/operator-inequality-multiset-stl-clr.md)|Determines if a `multiset` object is not equal to another `multiset` object.|  
|[operator\< \(multiset\)](../dotnet/operator-less-than-multiset-stl-clr.md)|Determines if a `multiset` object is less than another `multiset` object.|  
|[operator\<\= \(multiset\)](../dotnet/operator-less-or-equal-multiset-stl-clr.md)|Determines if a `multiset` object is less than or equal to another `multiset` object.|  
|[operator\=\= \(multiset\)](../dotnet/operator-equality-multiset-stl-clr.md)|Determines if a `multiset` object is equal to another `multiset` object.|  
|[operator\> \(multiset\)](../dotnet/operator-greater-than-multiset-stl-clr.md)|Determines if a `multiset` object is greater than another `multiset` object.|  
|[operator\>\= \(multiset\)](../dotnet/operator-greater-or-equal-multiset-stl-clr.md)|Determines if a `multiset` object is greater than or equal to another `multiset` object.|  
  
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
  
 The object orders the sequence it controls by calling a stored delegate object of type [multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md).  You can specify the stored delegate object when you construct the multiset; if you specify no delegate object, the default is the comparison `operator<(key_type, key_type)`.  You access this stored object by calling the member function [multiset::key\_comp](../dotnet/multiset-key-comp-stl-clr.md)`()`.  
  
 Such a delegate object must impose a strict weak ordering on keys of type [multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md).  That means, for any two keys `X` and `Y`:  
  
 `key_comp()(X, Y)` returns the same Boolean result on every call.  
  
 If `key_comp()(X, Y)` is true, then `key_comp()(Y, X)` must be false.  
  
 If `key_comp()(X, Y)` is true, then `X` is said to be ordered before `Y`.  
  
 If `!key_comp()(X, Y) && !key_comp()(Y, X)` is true, then `X` and `Y` are said to have equivalent ordering.  
  
 For any element `X` that precedes `Y` in the controlled sequence, `key_comp()(Y, X)` is false. \(For the default delegate object, keys never decrease in value.\) Unlike template class [set](../dotnet/set-stl-clr.md), an object of template class `multiset` does not require that keys for all elements are unique. \(Two or more keys can have equivalent ordering.\)  
  
 Each element serves as both a ey and a value.  The sequence is represented in a way that permits lookup, insertion, and removal of an arbitrary element with a number of operations proportional to the logarithm of the number of elements in the sequence \(logarithmic time\).  Moreover, inserting an element invalidates no iterators, and removing an element invalidates only those iterators which point at the removed element.  
  
 A multiset supports bidirectional iterators, which means you can step to adjacent elements given an iterator that designates an element in the controlled sequence.  A special head node corresponds to the iterator returned by [multiset::end](../dotnet/multiset-end-stl-clr.md)`()`.  You can decrement this iterator to reach the last element in the controlled sequence, if present.  You can increment a multiset iterator to reach the head node, and it will then compare equal to `end()`.  But you cannot dereference the iterator returned by `end()`.  
  
 Note that you cannot refer to a multiset element directly given its numerical position \-\- that requires a random\-access iterator.  
  
 A multiset iterator stores a handle to its associated multiset node, which in turn stores a handle to its associated container.  You can use iterators only with their associated container objects.  A multiset iterator remains valid so long as its associated multiset node is associated with some multiset.  Moreover, a valid iterator is dereferencable \-\- you can use it to access or alter the element value it designates \-\- so long as it is not equal to `end()`.  
  
 Erasing or removing an element calls the destructor for its stored value.  Destroying the container erases all elements.  Thus, a container whose element type is a ref class ensures that no elements outlive the container.  Note, however, that a container of handles does `not` destroy its elements.  
  
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)