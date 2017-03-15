---
title: "list(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/list> 헤더[STL/CLR]"
  - "<list> 헤더[STL/CLR]"
  - "목록 클래스[STL/CLR]"
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# list(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that controls a varying\-length sequence of elements that has bidirectional access.  You use the container `list` to manage a sequence of elements as a bidirectional linked list of nodes, each storing one element.  
  
 In the description below, `GValue` is the same as `Value` unless the latter is a ref type, in which case it is `Value^`.  
  
## 구문  
  
```  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
#### 매개 변수  
 값  
 제어되는 시퀀스의 요소 형식입니다.  
  
## 멤버  
  
|Type Definition|설명|  
|---------------------|--------|  
|[list::const\_iterator](../dotnet/list-const-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[list::const\_reference](../dotnet/list-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[list::const\_reverse\_iterator](../dotnet/list-const-reverse-iterator-stl-clr.md)|The type of a constant reverse iterator for the controlled sequence.|  
|[list::difference\_type](../dotnet/list-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[list::generic\_container](../dotnet/list-generic-container-stl-clr.md)|The type of the generic interface for the container.|  
|[list::generic\_iterator](../dotnet/list-generic-iterator-stl-clr.md)|The type of an iterator for the generic interface for the container.|  
|[list::generic\_reverse\_iterator](../dotnet/list-generic-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the generic interface for the container.|  
|[list::generic\_value](../dotnet/list-generic-value-stl-clr.md)|The type of an element for the generic interface for the container.|  
|[list::iterator](../dotnet/list-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[list::reference](../dotnet/list-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[list::reverse\_iterator](../dotnet/list-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the controlled sequence.|  
|[list::size\_type](../dotnet/list-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[list::value\_type](../dotnet/list-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|Member Function|설명|  
|---------------------|--------|  
|[list::assign](../dotnet/list-assign-stl-clr.md)|Replaces all elements.|  
|[list::back](../dotnet/list-back-stl-clr.md)|Accesses the last element.|  
|[list::begin](../dotnet/list-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[list::clear](../dotnet/list-clear-stl-clr.md)|Removes all elements.|  
|[list::empty](../dotnet/list-empty-stl-clr.md)|Tests whether no elements are present.|  
|[list::end](../dotnet/list-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[list::erase](../dotnet/list-erase-stl-clr.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[list::front](../dotnet/list-front-stl-clr.md)|Accesses the first element.|  
|[list::insert](../dotnet/list-insert-stl-clr.md)|Adds elements at a specified position.|  
|[list::list](../dotnet/list-list-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[list::merge](../dotnet/list-merge-stl-clr.md)|순서가 지정된 두 개의 제어되는 시퀀스를 병합합니다.|  
|[list::pop\_back](../dotnet/list-pop-back-stl-clr.md)|Removes the last element.|  
|[list::pop\_front](../dotnet/list-pop-front-stl-clr.md)|Removes the first element.|  
|[list::push\_back](../dotnet/list-push-back-stl-clr.md)|Adds a new last element.|  
|[list::push\_front](../dotnet/list-push-front-stl-clr.md)|Adds a new first element.|  
|[list::rbegin](../dotnet/list-rbegin-stl-clr.md)|역방향 제어되는 시퀀스의 시작을 지정합니다.|  
|[list::remove](../dotnet/list-remove-stl-clr.md)|Removes an element with a specified value.|  
|[list::remove\_if](../dotnet/list-remove-if-stl-clr.md)|Removes elements that pass a specified test.|  
|[list::rend](../dotnet/list-rend-stl-clr.md)|역방향 제어되는 시퀀스의 끝을 지정합니다.|  
|[list::resize](../dotnet/list-resize-stl-clr.md)|요소 수를 변경합니다.|  
|[list::reverse](../dotnet/list-reverse-stl-clr.md)|Reverses the controlled sequence.|  
|[list::size](../dotnet/list-size-stl-clr.md)|요소의 수를 셉니다.|  
|[list::sort](../dotnet/list-sort-stl-clr.md)|제어되는 시퀀스를 정렬합니다.|  
|[list::splice](../dotnet/list-splice-stl-clr.md)|restitches는 노드사이를 연결합니다.|  
|[list::swap](../dotnet/list-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
|[list::to\_array](../dotnet/list-to-array-stl-clr.md)|Copies the controlled sequence to a new array.|  
|[list::unique](../dotnet/list-unique-stl-clr.md)|지정된 테스트를 통과하는 인접 요소를 제거합니다.|  
  
|Property|설명|  
|--------------|--------|  
|[list::back\_item](../dotnet/list-back-item-stl-clr.md)|Accesses the last element.|  
|[list::front\_item](../dotnet/list-front-item-stl-clr.md)|Accesses the first element.|  
  
|연산자|설명|  
|---------|--------|  
|[list::operator\=](../dotnet/list-operator-assign-stl-clr.md)|Replaces the controlled sequence.|  
|[operator\!\= \(list\)](../dotnet/operator-inequality-list-stl-clr.md)|Determines if a `list` object is not equal to another `list` object.|  
|[operator\< \(list\)](../dotnet/operator-less-than-list-stl-clr.md)|Determines if a `list` object is less than another `list` object.|  
|[operator\<\= \(list\)](../dotnet/operator-less-or-equal-list-stl-clr.md)|Determines if a `list` object is less than or equal to another `list` object.|  
|[operator\=\= \(list\)](../dotnet/operator-equality-list-stl-clr.md)|Determines if a `list` object is equal to another `list` object.|  
|[operator\> \(list\)](../dotnet/operator-greater-than-list-stl-clr.md)|Determines if a `list` object is greater than another `list` object.|  
|[operator\>\= \(list\)](../dotnet/operator-greater-or-equal-list-stl-clr.md)|Determines if a `list` object is greater than or equal to another `list` object.|  
  
## 인터페이스  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:System.ICloneable>|Duplicate an object.|  
|<xref:System.Collections.IEnumerable>|Sequence through elements.|  
|<xref:System.Collections.ICollection>|Maintain group of elements.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Sequence through typed elements.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintain group of typed elements.|  
|IList\<Value\>|Maintain generic container.|  
  
## 설명  
 The object allocates and frees storage for the sequence it controls as individual nodes in a bidirectional link list.  It rearranges elements by altering the links between nodes, never by copying the contents of one node to another.  That means you can insert and remove elements freely without disturbing remaining elements.  Thus, a list is a good candidate for the underlying container for template class [queue](../dotnet/queue-stl-clr.md) or template class [stack](../dotnet/stack-stl-clr.md).  
  
 A `list` object supports bidirectional iterators, which means you can step to adjacent elements given an iterator that designates an element in the controlled sequence.  A special head node corresponds to the iterator returned by [list::end](../dotnet/list-end-stl-clr.md)`()`.  You can decrement this iterator to reach the last element in the controlled sequence, if present.  You can increment a list iterator to reach the head node, and it will then compare equal to `end()`.  But you cannot dereference the iterator returned by `end()`.  
  
 Note that you cannot refer to a list element directly given its numerical position \-\- that requires a random\-access iterator.  So a list is `not` usable as the underlying container for template class [priority\_queue](../dotnet/priority-queue-stl-clr.md).  
  
 A list iterator stores a handle to its associated list node, which in turn stores a handle to its associated container.  You can use iterators only with their associated container objects.  A list iterator remains valid so long as its associated list node is associated with some list.  Moreover, a valid iterator is dereferencable \-\- you can use it to access or alter the element value it designates \-\- so long as it is not equal to `end()`.  
  
 Erasing or removing an element calls the destructor for its stored value.  Destroying the container erases all elements.  Thus, a container whose element type is a ref class ensures that no elements outlive the container.  Note, however, that a container of handles does `not` destroy its elements.  
  
## 요구 사항  
 **Header:** \<cliext\/list\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [stack](../dotnet/stack-stl-clr.md)   
 [vector](../dotnet/vector-stl-clr.md)   
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)