---
title: "vector(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/vector> 헤더[STL/CLR]"
  - "<vector> 헤더[STL/CLR]"
  - "vector 클래스[STL/CLR]"
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# vector(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that controls a varying\-length sequence of elements that has random access.  You use the container `vector` to manage a sequence of elements as a contiguous block of storage.  The block is implemented as an array that grows on demand.  
  
 In the description below, `GValue` is the same as `Value` unless the latter is a ref type, in which case it is `Value^`.  
  
## 구문  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
#### 매개 변수  
 값  
 제어되는 시퀀스의 요소 형식입니다.  
  
## 멤버  
  
|Type Definition|설명|  
|---------------------|--------|  
|[vector::const\_iterator](../dotnet/vector-const-iterator-stl-clr.md)|제어되는 시퀀스에 대한 상수 반복기의 형식입니다.|  
|[vector::const\_reference](../dotnet/vector-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[vector::const\_reverse\_iterator](../dotnet/vector-const-reverse-iterator-stl-clr.md)|The type of a constant reverse iterator for the controlled sequence.|  
|[vector::difference\_type](../dotnet/vector-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[vector::generic\_container](../dotnet/vector-generic-container-stl-clr.md)|The type of the generic interface for the container.|  
|[vector::generic\_iterator](../dotnet/vector-generic-iterator-stl-clr.md)|The type of an iterator for the generic interface for the container.|  
|[vector::generic\_reverse\_iterator](../dotnet/vector-generic-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the generic interface for the container.|  
|[vector::generic\_value](../dotnet/vector-generic-value-stl-clr.md)|The type of an element for the generic interface for the container.|  
|[vector::iterator](../dotnet/vector-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[vector::reference](../dotnet/vector-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[vector::reverse\_iterator](../dotnet/vector-reverse-iterator-stl-clr.md)|The type of a reverse iterator for the controlled sequence.|  
|[vector::size\_type](../dotnet/vector-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[vector::value\_type](../dotnet/vector-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|Member Function|설명|  
|---------------------|--------|  
|[vector::assign](../dotnet/vector-assign-stl-clr.md)|Replaces all elements.|  
|[vector::at](../dotnet/vector-at-stl-clr.md)|Accesses an element at a specified position.|  
|[vector::back](../dotnet/vector-back-stl-clr.md)|Accesses the last element.|  
|[vector::begin](../dotnet/vector-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[vector::capacity](../dotnet/vector-capacity-stl-clr.md)|컨테이너에 할당된 저장소의 크기를 보고합니다.|  
|[vector::clear](../dotnet/vector-clear-stl-clr.md)|Removes all elements.|  
|[vector::empty](../dotnet/vector-empty-stl-clr.md)|Tests whether no elements are present.|  
|[vector::end](../dotnet/vector-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[vector::erase](../dotnet/vector-erase-stl-clr.md)|지정된 위치에 있는 요소를 제거합니다.|  
|[vector::front](../dotnet/vector-front-stl-clr.md)|Accesses the first element.|  
|[vector::insert](../dotnet/vector-insert-stl-clr.md)|Adds elements at a specified position.|  
|[vector::pop\_back](../dotnet/vector-pop-back-stl-clr.md)|Removes the last element.|  
|[vector::push\_back](../dotnet/vector-push-back-stl-clr.md)|Adds a new last element.|  
|[vector::rbegin](../dotnet/vector-rbegin-stl-clr.md)|역방향 제어되는 시퀀스의 시작을 지정합니다.|  
|[vector::rend](../dotnet/vector-rend-stl-clr.md)|역방향 제어되는 시퀀스의 끝을 지정합니다.|  
|[vector::reserve](../dotnet/vector-reserve-stl-clr.md)|Ensures a minimum growth capacity for the container.|  
|[vector::resize](../dotnet/vector-resize-stl-clr.md)|요소 수를 변경합니다.|  
|[vector::size](../dotnet/vector-size-stl-clr.md)|요소의 수를 셉니다.|  
|[vector::swap](../dotnet/vector-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
|[vector::to\_array](../dotnet/vector-to-array-stl-clr.md)|Copies the controlled sequence to a new array.|  
|[vector::vector](../dotnet/vector-vector-stl-clr.md)|컨테이너 개체를 만듭니다.|  
  
|Property|설명|  
|--------------|--------|  
|[vector::back\_item](../dotnet/vector-back-item-stl-clr.md)|Accesses the last element.|  
|[vector::front\_item](../dotnet/vector-front-item-stl-clr.md)|Accesses the first element.|  
  
|연산자|설명|  
|---------|--------|  
|[vector::operator\=](../dotnet/vector-operator-assign-stl-clr.md)|Replaces the controlled sequence.|  
|[vector::operator](../dotnet/vector-operator-stl-clr.md)|Accesses an element at a specified position.|  
|[operator\!\= \(vector\)](../dotnet/operator-inequality-vector-stl-clr.md)|Determines if a `vector` object is not equal to another `vector` object.|  
|[operator\< \(vector\)](../dotnet/operator-less-than-vector-stl-clr.md)|Determines if a `vector` object is less than another `vector` object.|  
|[operator\<\= \(vector\)](../dotnet/operator-less-or-equal-vector-stl-clr.md)|Determines if a `vector` object is less than or equal to another `vector` object.|  
|[operator\=\= \(vector\)](../dotnet/operator-equality-vector-stl-clr.md)|Determines if a `vector` object is equal to another `vector` object.|  
|[operator\> \(vector\)](../dotnet/operator-greater-than-vector-stl-clr.md)|Determines if a `vector` object is greater than another `vector` object.|  
|[operator\>\= \(vector\)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)|Determines if a `vector` object is greater than or equal to another `vector` object.|  
  
## 인터페이스  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:System.ICloneable>|Duplicate an object.|  
|<xref:System.Collections.IEnumerable>|Sequence through elements.|  
|<xref:System.Collections.ICollection>|Maintain group of elements.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Sequence through typed elements.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintain group of typed elements.|  
|<xref:System.Collections.Generic.IList%601>|Maintain ordered group of typed elements.|  
|IVector\<Value\>|Maintain generic container.|  
  
## 설명  
 The object allocates and frees storage for the sequence it controls through a stored array of `Value` elements, which grows on demand.  Growth occurs in such a way that the cost of appending a new element is amortized constant time.  In other words, the cost of adding elements at the end does not increase, on average, as the length of the controlled sequence gets larger.  Thus, a vector is a good candidate for the underlying container for template class [stack](../dotnet/stack-stl-clr.md).  
  
 A `vector` supports random\-access iterators, which means you can refer to an element directly given its numerical position, counting from zero for the first \(front\) element, to [vector::size](../dotnet/vector-size-stl-clr.md)`() - 1` for the last \(back\) element.  It also means that a vector is a good candidate for the underlying container for template class [priority\_queue](../dotnet/priority-queue-stl-clr.md).  
  
 A vector iterator stores a handle to its associated vector object, along with the bias of the element it designates.  You can use iterators only with their associated container objects.  The bias of a vector element is the same as its position.  
  
 Inserting or erasing elements can change the element value stored at a given position, so the value designated by an iterator can also change. \(The container may have to copy elements up or down to create a hole before an insert or to fill a hole after an erase.\) Nevertheless, a vector iterator remains valid so long as its bias is in the range `[0,` [vector::size](../dotnet/vector-size-stl-clr.md)`()]`.  Moreover, a valid iterator remains dereferencable \-\- you can use it to access or alter the element value it designates \-\- so long as its bias is not equal to `size()`.  
  
 Erasing or removing an element calls the destructor for its stored value.  Destroying the container erases all elements.  Thus, a container whose element type is a ref class ensures that no elements outlive the container.  Note, however, that a container of handles does `not` destroy its elements.  
  
## 요구 사항  
 **Header:** \<cliext\/vector\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [stack](../dotnet/stack-stl-clr.md)   
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)