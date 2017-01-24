---
title: "queue(STL/CLR) | Microsoft Docs"
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
  - "cliext::queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/queue> 헤더[STL/CLR]"
  - "<queue> 헤더[STL/CLR]"
  - "큐 클래스[STL/CLR]"
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# queue(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that controls a varying\-length sequence of elements that has first\-in first\-out access.  You use the container adapter `queue` to manage an underlying container as a queue.  
  
 In the description below, `GValue` is the same as `Value` unless the latter is a ref type, in which case it is `Value^`.  Similarly, `GContainer` is the same as `Container` unless the latter is a ref type, in which case it is `Container^`.  
  
## 구문  
  
```  
template<typename Value,  
    typename Container>  
    ref class queue  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>  
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
|[queue::const\_reference](../dotnet/queue-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[queue::container\_type](../dotnet/queue-container-type-stl-clr.md)|기본 컨테이너의 형식입니다.|  
|[queue::difference\_type](../dotnet/queue-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[queue::generic\_container](../dotnet/queue-generic-container-stl-clr.md)|The type of the generic interface for the container adapter.|  
|[queue::generic\_value](../dotnet/queue-generic-value-stl-clr.md)|The type of an element for the generic interface for the container adapter.|  
|[queue::reference](../dotnet/queue-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[queue::size\_type](../dotnet/queue-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[queue::value\_type](../dotnet/queue-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|Member Function|설명|  
|---------------------|--------|  
|[queue::assign](../dotnet/queue-assign-stl-clr.md)|Replaces all elements.|  
|[queue::back](../dotnet/queue-back-stl-clr.md)|Accesses the last element.|  
|[queue::empty](../dotnet/queue-empty-stl-clr.md)|Tests whether no elements are present.|  
|[queue::front](../dotnet/queue-front-stl-clr.md)|Accesses the first element.|  
|[queue::get\_container](../dotnet/queue-get-container-stl-clr.md)|기본 컨테이너에 액세스합니다.|  
|[queue::pop](../dotnet/queue-pop-stl-clr.md)|Removes the first element.|  
|[queue::push](../dotnet/queue-push-stl-clr.md)|Adds a new last element.|  
|[queue::queue](../dotnet/queue-queue-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[queue::size](../dotnet/queue-size-stl-clr.md)|요소의 수를 셉니다.|  
|[queue::to\_array](../dotnet/queue-to-array-stl-clr.md)|Copies the controlled sequence to a new array.|  
  
|Property|설명|  
|--------------|--------|  
|[queue::back\_item](../dotnet/queue-back-item-stl-clr.md)|Accesses the last element.|  
|[queue::front\_item](../dotnet/queue-front-item-stl-clr.md)|Accesses the first element.|  
  
|연산자|설명|  
|---------|--------|  
|[queue::operator\=](../dotnet/queue-operator-assign-stl-clr.md)|Replaces the controlled sequence.|  
|[operator\!\= \(queue\)](../dotnet/operator-inequality-queue-stl-clr.md)|Determines if a `queue` object is not equal to another `queue` object.|  
|[operator\< \(queue\)](../dotnet/operator-less-than-queue-stl-clr.md)|Determines if a `queue` object is less than another `queue` object.|  
|[operator\<\= \(queue\)](../dotnet/operator-less-or-equal-queue-stl-clr.md)|Determines if a `queue` object is less than or equal to another `queue` object.|  
|[operator\=\= \(queue\)](../dotnet/operator-equality-queue-stl-clr.md)|Determines if a `queue` object is equal to another `queue` object.|  
|[operator\> \(queue\)](../dotnet/operator-greater-than-queue-stl-clr.md)|Determines if a `queue` object is greater than another `queue` object.|  
|[operator\>\= \(queue\)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)|Determines if a `queue` object is greater than or equal to another `queue` object.|  
  
## 인터페이스  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:System.ICloneable>|Duplicate an object.|  
|IQueue\<Value, Container\>|Maintain generic container adapter.|  
  
## 설명  
 The object allocates and frees storage for the sequence it controls through an underlying container, of type `Container`, that stores `Value` elements and grows on demand.  The object restricts access to just pushing the first element and popping the last element, implementing a first\-in first\-out queue \(also known as a FIFO queue, or simply a queue\).  
  
## 요구 사항  
 **Header:** \<cliext\/queue\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [stack](../dotnet/stack-stl-clr.md)   
 [vector](../dotnet/vector-stl-clr.md)   
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)