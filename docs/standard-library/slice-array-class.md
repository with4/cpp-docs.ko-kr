---
title: "slice_array 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "slice_array"
  - "valarray/std::slice_array"
  - "std.slice_array"
  - "std::slice_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "slice_array 클래스"
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# slice_array 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An internal, auxiliary template class that supports slice objects by providing operations between subset arrays defined by the slice of a valarray.  
  
## 구문  
  
```  
template<class Type>  
   class slice_array : public slice {  
public:  
   typedef Type value_type;  
   void operator=(  
      const valarray<Type>& x  
   ) const;  
   void operator=(  
      const Type& x  
   ) const;  
   void operator*=(  
      const valarray<Type>& x  
   ) const;  
   void operator/=(  
      const valarray<Type>& x  
   ) const;  
   void operator%=(  
      const valarray<Type>& x  
   ) const;  
   void operator+=(  
      const valarray<Type>& x  
   ) const;  
   void operator-=(  
      const valarray<Type>& x  
   ) const;  
   void operator^=(  
      const valarray<Type>& x  
   ) const;  
   void operator&=(  
      const valarray<Type>& x  
   ) const;  
   void operator|=(  
      const valarray<Type>& x  
   ) const;  
   void operator<<=(  
      const valarray<Type>& x  
   ) const;  
   void operator>>=(  
      const valarray<Type>& x  
   ) const;  
// The rest is private or implementation defined  
}  
```  
  
## 설명  
 The class describes an object that stores a reference to an object of class [valarray](../standard-library/valarray-class.md)**\<Type\>**, along with an object of class [slice](../standard-library/slice-class.md), which describes the sequence of elements to select from the **valarray\<Type\>** object.  
  
 The template class is created indirectly by certain valarray operations and cannot be used directly in the program.  An internal, auxiliary template class that is used by the slice subscript operator:  
  
 `slice_array`\<**Type**\> `valarray`\<**Type**::`operator[]` \(`slice`\).  
  
 You construct a **slice\_array\<Type\>** object only by writing an expression of the form [va&#91;sl&#93;](../Topic/valarray::operator.md), for a slice **sl** of valarray **va**.  The member functions of class slice\_array then behave like the corresponding function signatures defined for **valarray\<Type\>**, except that only the sequence of selected elements is affected.  The sequence controlled by the slice\_array is defined by the three parameters of the slice constructor, the index of the first element in the slice, the number of elements, and the distance between the elements.  A slice\_array cut from valarray **va** declared by **va**\[`slice`\(2, 5, 3\)\] selects elements with indices 2, 5, 8, 11, and 14 from **va**.  The indices must be valid for the procedure to be valid.  
  
## 예제  
 See the example for [slice::slice](../Topic/slice::slice.md) for an example of how to declare and use a slice\_array.  
  
## 요구 사항  
 **Header:** \<valarray\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)