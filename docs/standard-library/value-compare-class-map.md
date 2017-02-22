---
title: "value_compare 클래스(&lt;map&gt;) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::value_compare"
  - "std.value_compare"
  - "map/std::value_compare"
  - "value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare 클래스"
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# value_compare 클래스(&lt;map&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Provides a function object that can compare the elements of a map by comparing the values of their keys to determine their relative order in the map.  
  
## 구문  
  
```  
class value_compare : public binary_function<value_type, value_type, bool>  
{  
public:  
   bool operator()(const value_type& _Left, const value_type& _Right) const;  
   value_compare(key_compare _Pred) : comp(_Pred);  
   protected:  
      key_compare comp;  
};  
```  
  
## 설명  
 The comparison criterion provided by `value_compare` between **value\_types** of whole elements contained by a map is induced from a comparison between the keys of the respective elements by the auxiliary class construction.  The member function operator uses the object **comp** of type `key_compare` stored in the function object provided by `value_compare` to compare the sort\-key components of two elements.  
  
 For sets and multisets, which are simple containers where the key values are identical to the element values, `value_compare` is equivalent to `key_compare`; for maps and multimaps they are not, as the value of the type `pair` elements is not identical to the value of the element's key.  
  
## 예제  
 See example for [value\_comp](../Topic/map::value_comp.md) for an example of how to declare and use `value_compare`.  
  
## 요구 사항  
 **헤더:** \<맵\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [binary\_function 구조체](../standard-library/binary-function-struct.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)