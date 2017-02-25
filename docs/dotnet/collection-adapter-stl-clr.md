---
title: "collection_adapter(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::collection_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collection_adapter 클래스[STL/CLR]"
ms.assetid: 31964058-1f50-48bf-82c2-b0b3cc8a7887
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# collection_adapter(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wraps a .NET collection for use as an STL\/CLR container.  A `collection_adapter` is a template class that describes a simple STL\/CLR container object.  It wraps a Base Class Library \(BCL\) interface, and returns an iterator pair that you use to manipulate the controlled sequence.  
  
## 구문  
  
```  
template<typename Coll>  
    ref class collection_adapter;  
  
template<>  
    ref class collection_adapter<  
        System::Collections::ICollection>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IEnumerable>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IList>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IDictionary>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::ICollection<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IEnumerable<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IList<Value>>;  
template<typename Key,  
    typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IDictionary<Key, Value>>;  
```  
  
#### 매개 변수  
 Coll  
 The type of the wrapped collection.  
  
## 특수화  
  
|Specialization|설명|  
|--------------------|--------|  
|IEnumerable|Sequences through elements.|  
|ICollection|Maintains a group of elements.|  
|IList|Maintains an ordered group of elements.|  
|IDictionary|Maintain a set of {key, value} pairs.|  
|IEnumerable\<Value\>|Sequences through typed elements.|  
|ICollection\<Value\>|Maintains a group of typed elements.|  
|IList\<Value\>|Maintains an ordered group of typed elements.|  
|IDictionary\<Value\>|Maintains a set of typed {key, value} pairs.|  
  
## 멤버  
  
|Type Definition|설명|  
|---------------------|--------|  
|[collection\_adapter::difference\_type](../dotnet/collection-adapter-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[collection\_adapter::iterator](../dotnet/collection-adapter-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[collection\_adapter::key\_type](../dotnet/collection-adapter-key-type-stl-clr.md)|The type of a dictionary key.|  
|[collection\_adapter::mapped\_type](../dotnet/collection-adapter-mapped-type-stl-clr.md)|The type of a dictionary value.|  
|[collection\_adapter::reference](../dotnet/collection-adapter-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[collection\_adapter::size\_type](../dotnet/collection-adapter-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[collection\_adapter::value\_type](../dotnet/collection-adapter-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|Member Function|설명|  
|---------------------|--------|  
|[collection\_adapter::base](../dotnet/collection-adapter-base-stl-clr.md)|Designates the wrapped BCL interface.|  
|[collection\_adapter::begin](../dotnet/collection-adapter-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[collection\_adapter::collection\_adapter](../dotnet/collection-adapter-collection-adapter-stl-clr.md)|Constructs an adapter object.|  
|[collection\_adapter::end](../dotnet/collection-adapter-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[collection\_adapter::size](../dotnet/collection-adapter-size-stl-clr.md)|요소의 수를 셉니다.|  
|[collection\_adapter::swap](../dotnet/collection-adapter-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
  
|연산자|설명|  
|---------|--------|  
|[collection\_adapter::operator\=](../dotnet/collection-adapter-operator-assign-stl-clr.md)|Replaces the stored BCL handle.|  
  
## 설명  
 You use this template class to manipulate a BCL container as a STL\/CLR container.  The `collection_adapter` stores a handle to a BCL interface, which in turn controls a sequence of elements.  A `collection_adapter` object `X` returns a pair of input iterators `X.begin()` and `X.end()` that you use to visit the elements, in order.  Some of the specializations also let you write `X.size()` to determine the length of the controlled sequence.  
  
## 요구 사항  
 **Header:** \<cliext\/adapter\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)   
 [make\_collection](../dotnet/make-collection-stl-clr.md)