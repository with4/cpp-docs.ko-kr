---
title: "stack(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/stack> 헤더[STL/CLR]"
  - "<stack> 헤더[STL/CLR]"
  - "스택 클래스[STL/CLR]"
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# stack(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The template class describes an object that controls a varying\-length sequence of elements that has last\-in first\-out access.  You use the container adapter `stack` to manage an underlying container as a push\-down stack.  
  
 In the description below, `GValue` is the same as `Value` unless the latter is a ref type, in which case it is `Value^`.  Similarly, `GContainer` is the same as `Container` unless the latter is a ref type, in which case it is `Container^`.  
  
## 구문  
  
```  
template<typename Value,  
    typename Container>  
    ref class stack  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>  
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
|[stack::const\_reference](../dotnet/stack-const-reference-stl-clr.md)|요소에 대한 상수 참조의 형식입니다.|  
|[stack::container\_type](../dotnet/stack-container-type-stl-clr.md)|기본 컨테이너의 형식입니다.|  
|[stack::difference\_type](../dotnet/stack-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[stack::generic\_container](../dotnet/stack-generic-container-stl-clr.md)|The type of the generic interface for the container adapter.|  
|[stack::generic\_value](../dotnet/stack-generic-value-stl-clr.md)|The type of an element for the generic interface for the container adapter.|  
|[stack::reference](../dotnet/stack-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[stack::size\_type](../dotnet/stack-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[stack::value\_type](../dotnet/stack-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|Member Function|설명|  
|---------------------|--------|  
|[stack::assign](../dotnet/stack-assign-stl-clr.md)|Replaces all elements.|  
|[stack::empty](../dotnet/stack-empty-stl-clr.md)|Tests whether no elements are present.|  
|[stack::get\_container](../dotnet/stack-get-container-stl-clr.md)|기본 컨테이너에 액세스합니다.|  
|[stack::pop](../dotnet/stack-pop-stl-clr.md)|Removes the last element.|  
|[stack::push](../dotnet/stack-push-stl-clr.md)|Adds a new last element.|  
|[stack::size](../dotnet/stack-size-stl-clr.md)|요소의 수를 셉니다.|  
|[stack::stack](../dotnet/stack-stack-stl-clr.md)|컨테이너 개체를 만듭니다.|  
|[stack::top](../dotnet/stack-top-stl-clr.md)|Accesses the last element.|  
|[stack::to\_array](../dotnet/stack-to-array-stl-clr.md)|Copies the controlled sequence to a new array.|  
  
|Property|설명|  
|--------------|--------|  
|[stack::top\_item](../dotnet/stack-top-item-stl-clr.md)|Accesses the last element.|  
  
|연산자|설명|  
|---------|--------|  
|[stack::operator\=](../dotnet/stack-operator-assign-stl-clr.md)|Replaces the controlled sequence.|  
|[operator\!\= \(stack\)](../dotnet/operator-inequality-stack-stl-clr.md)|Determines if a `stack` object is not equal to another `stack` object.|  
|[operator\< \(stack\)](../dotnet/operator-less-than-stack-stl-clr.md)|Determines if a `stack` object is less than another `stack` object.|  
|[operator\<\= \(stack\)](../dotnet/operator-less-or-equal-stack-stl-clr.md)|Determines if a `stack` object is less than or equal to another `stack` object.|  
|[operator\=\= \(stack\)](../dotnet/operator-equality-stack-stl-clr.md)|Determines if a `stack` object is equal to another `stack` object.|  
|[operator\> \(stack\)](../dotnet/operator-greater-than-stack-stl-clr.md)|Determines if a `stack` object is greater than another `stack` object.|  
|[operator\>\= \(stack\)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)|Determines if a `stack` object is greater than or equal to another `stack` object.|  
  
## 인터페이스  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:System.ICloneable>|Duplicate an object.|  
|IStack\<Value, Container\>|Maintain generic container adapter.|  
  
## 설명  
 The object allocates and frees storage for the sequence it controls through an underlying container, of type `Container`, that stores `Value` elements and grows on demand.  The object restricts access to pushing and popping just the last element, implementing a last\-in first\-out queue \(also known as a LIFO queue, or stack\).  
  
## 요구 사항  
 **Header:** \<cliext\/stack\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [vector](../dotnet/vector-stl-clr.md)   
 [STL\/CLR 라이브러리](../dotnet/stl-clr-library-reference.md)