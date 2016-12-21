---
title: "range_adapter(STL/CLR) | Microsoft Docs"
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
  - "cliext::range_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "range_adapter 클래스[STL/CLR]"
ms.assetid: 3fbe2a65-1216-46a0-a182-422816b80cfb
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# range_adapter(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A template class that wraps a pair of iterators that are used to implement several Base Class Library \(BCL\) interfaces.  You use the range\_adapter to manipulate an STL\/CLR range as if it were a BCL collection.  
  
## 구문  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### 매개 변수  
 Iter  
 The type associated with the wrapped iterators.  
  
## 멤버  
  
|Member Function|설명|  
|---------------------|--------|  
|[range\_adapter::range\_adapter](../dotnet/range-adapter-range-adapter-stl-clr.md)|Constructs an adapter object.|  
  
|연산자|설명|  
|---------|--------|  
|[range\_adapter::operator\=](../dotnet/range-adapter-operator-assign-stl-clr.md)|Replaces the stored iterator pair.|  
  
## 인터페이스  
  
|인터페이스|설명|  
|-----------|--------|  
|<xref:System.Collections.IEnumerable>|Iterates through elements in the collection.|  
|<xref:System.Collections.ICollection>|Maintains a group of elements.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Iterates through typed elements in the collection..|  
|<xref:System.Collections.Generic.ICollection%601>|Maintains a group of typed elements.|  
  
## 설명  
 The range\_adapter stores a pair of iterators, which in turn delimit a sequence of elements.  The object implements four BCL interfaces that let you iterate through the elements, in order.  You use this template class to manipulate STL\/CLR ranges much like BCL containers.  
  
## 요구 사항  
 **Header:** \<cliext\/adapter\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [collection\_adapter](../dotnet/collection-adapter-stl-clr.md)   
 [make\_collection](../dotnet/make-collection-stl-clr.md)