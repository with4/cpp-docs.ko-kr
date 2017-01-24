---
title: "클래스 value_compare 클래스 | Microsoft Docs"
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
  - "std::value_compare"
  - "std.value_compare"
  - "value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare 클래스"
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 클래스 value_compare 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Provides a function object that can compare the elements of a hash\_map by comparing the values of their keys to determine their relative order in the hash\_map.  
  
## 구문  
  
```  
class value_compare  
    : std::public binary_function<value_type, value_type, bool>   
{  
public:  
    bool operator( )(  
        const value_type& _Left,  
        const value_type& _Right ) const  
        {  
            return ( comp( _Left.first, _Right.first ) );   
        }  
protected:  
    value_compare( const key_compare& c ) : comp (c) { }  
    key_compare comp;  
};  
```  
  
## 설명  
 The comparison criteria provided by value\_compare between **value\_types** of whole elements contained by a hash\_map is induced from a comparison between the keys of the respective elements by the auxiliary class construction.  The member function operator uses the object **comp** of type `key_compare` stored in the function object provided by value\_compare to compare the sort\-key components of two elements.  
  
 For hash\_sets and hash\_multisets, which are simple containers where the key values are identical to the element values, value\_compare is equivalent to `key_compare`; for hash\_maps and hash\_multimaps they are not, because the value of the type `pair` elements is not identical to the value of the element's key.  
  
 Visual C\+\+.NET 2003에서, [\<hash\_map\>](../standard-library/hash-map.md) 및 [\<hash\_set\>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 존재하지 않습니다. 대신 stdext 네임스페이스로 이동되었습니다.  자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하십시오.  
  
## 예제  
 See the example for [hash\_map::value\_comp](../Topic/hash_map::value_comp.md) for an example of how to declare and use value\_compare.  
  
## 요구 사항  
 **헤더:** \<hash\_map\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [binary\_function 구조체](../standard-library/binary-function-struct.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)