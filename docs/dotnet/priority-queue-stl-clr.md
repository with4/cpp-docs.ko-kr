---
title: "priority_queue(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/queue> 헤더[STL/CLR]"
  - "<queue> 헤더[STL/CLR]"
  - "priority_queue 클래스[STL/CLR]"
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# priority_queue(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that controls a varying\-length ordered sequence of elements that has limited access.  You use the container adapter `priority_queue` to manage an underlying container as a priority queue.  
  
 In the description below, `GValue` is the same as `Value` unless the latter is a ref type, in which case it is `Value^`.  Similarly, `GContainer` is the same as `Container` unless the latter is a ref type, in which case it is `Container^`.  
  
## 구문  
  
```  
template<typename Value,  
    typename Container>  
    ref class priority_queue  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>  
    { ..... };  
```  
  
#### 매개 변수  
 값  
 제어되는 시퀀스의 요소 형식입니다.  
  
 컨테이너  
 기본 컨테이너의 형식입니다.  
  
## 멤버  
  
|Type Definition|설명|  
|---------------------|--------|  
|[priority\_queue::const\_reference](../dotnet/priority-queue-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[priority\_queue::container\_type](../dotnet/priority-queue-container-type-stl-clr.md)|기본 컨테이너의 형식입니다.|  
|[priority\_queue::difference\_type](../dotnet/priority-queue-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[priority\_queue::generic\_container](../dotnet/priority-queue-generic-container-stl-clr.md)|The type of the generic interface for the container adapter.|  
|[priority\_queue::generic\_value](../dotnet/priority-queue-generic-value-stl-clr.md)|The type of an element for the generic interface for the container adapter.|  
|[priority\_queue::reference](../dotnet/priority-queue-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[priority\_queue::size\_type](../dotnet/priority-queue-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[priority\_queue::value\_compare](../dotnet/priority-queue-value-compare-stl-clr.md)|The ordering delegate for two elements.|  
|[priority\_queue::value\_type](../dotnet/priority-queue-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|Member Function|설명|  
|---------------------|--------|  
|[priority\_queue::assign](../dotnet/priority-queue-assign-stl-clr.md)|Replaces all elements.|  
|[priority\_queue::empty](../dotnet/priority-queue-empty-stl-clr.md)|Tests whether no elements are present.|  
|[priority\_queue::get\_container](../dotnet/priority-queue-get-container-stl-clr.md)|기본 컨테이너에 액세스합니다.|  
|[priority\_queue::pop](../dotnet/priority-queue-pop-stl-clr.md)|Removes the hghest\-priority element.|  
|[priority\_queue::priority\_queue](../dotnet/priority-queue-priority-queue-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[priority\_queue::push](../dotnet/priority-queue-push-stl-clr.md)|Adds a new element.|  
|[priority\_queue::size](../dotnet/priority-queue-size-stl-clr.md)|요소의 수를 셉니다.|  
|[priority\_queue::top](../dotnet/priority-queue-top-stl-clr.md)|Accesses the highest\-priority element.|  
|[priority\_queue::to\_array](../dotnet/priority-queue-to-array-stl-clr.md)|Copies the controlled sequence to a new array.|  
|[priority\_queue::value\_comp](../dotnet/priority-queue-value-comp-stl-clr.md)|두 요소의 순서 지정 대리자를 복사합니다.|  
  
|Property|설명|  
|--------------|--------|  
|[priority\_queue::top\_item](../dotnet/priority-queue-top-item-stl-clr.md)|Accesses the highest\-priority element.|  
  
|연산자|설명|  
|---------|--------|  
|[priority\_queue::operator\=](../dotnet/priority-queue-operator-assign-stl-clr.md)|Replaces the controlled sequence.|  
  
## 인터페이스  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:System.ICloneable>|Duplicate an object.|  
|IPriorityQueue\<Value, Container\>|Maintain generic container adapter.|  
  
## 설명  
 The object allocates and frees storage for the sequence it controls through an underlying container, of type `Container`, that stores `Value` elements and grows on demand.  It keeps the sequence ordered as a heap, with the highest\-priority element \(the top element\) readily accessible and removable.  The object restricts access to pushing new elements and popping just the highest\-priority element, implementing a priority queue.  
  
 The object orders the sequence it controls by calling a stored delegate object of type [priority\_queue::value\_compare](../dotnet/priority-queue-value-compare-stl-clr.md).  You can specify the stored delegate object when you construct the priority\_queue; if you specify no delegate object, the default is the comparison `operator<(value_type, value_type)`.  You access this stored object by calling the member function [priority\_queue::value\_comp](../dotnet/priority-queue-value-comp-stl-clr.md)`()`.  
  
 Such a delegate object must impose a strict weak ordering on values of type [priority\_queue::value\_type](../dotnet/priority-queue-value-type-stl-clr.md).  That means, for any two keys `X` and `Y`:  
  
 `value_comp()(X, Y)` returns the same Boolean result on every call.  
  
 If `value_comp()(X, Y)` is true, then `value_comp()(Y, X)` must be false.  
  
 If `value_comp()(X, Y)` is true, then `X` is said to be ordered before `Y`.  
  
 If `!value_comp()(X, Y) && !value_comp()(Y, X)` is true, then `X` and `Y` are said to have equivalent ordering.  
  
 For any element `X` that precedes `Y` in the controlled sequence, `key_comp()(Y, X)` is false. \(For the default delegate object, keys never decrease in value.\)  
  
 The highest priority element is thus one of the elements which is not ordered before any other element.  
  
 Since the underlying container keeps elements ordered as a heap:  
  
 The container must support random\-access iterators.  
  
 Elements with equivalent ordering may be popped in a different order than they were pushed. \(The ordering is not stable.\)  
  
 Thus, candidates for the underlying container include [deque](../dotnet/deque-stl-clr.md) and [vector](../dotnet/vector-stl-clr.md).  
  
## 요구 사항  
 **Header:** \<cliext\/queue\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [stack](../dotnet/stack-stl-clr.md)   
 [vector](../dotnet/vector-stl-clr.md)   
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)