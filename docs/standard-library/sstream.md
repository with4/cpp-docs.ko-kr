---
title: "&lt;sstream&gt; | Microsoft Docs"
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
  - "std.<sstream>"
  - "std::<sstream>"
  - "<sstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sstream 헤더"
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
caps.latest.revision: 20
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;sstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Defines several template classes that support iostreams operations on sequences stored in an allocated array object.  Such sequences are easily converted to and from objects of template class [basic\_string](../standard-library/basic-string-class.md).  
  
## 구문  
  
```  
namespace std {  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_stringbuf;  
typedef basic_stringbuf<char> stringbuf;  
typedef basic_stringbuf<wchar_t> wstringbuf;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_istringstream;  
typedef basic_istringstream<char> istringstream;  
typedef basic_istringstream<wchar_t> wistringstream;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_ostringstream;  
typedef basic_ostringstream<char> ostringstream;  
typedef basic_ostringstream<wchar_t> wostringstream;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_stringstream;  
typedef basic_stringstream<char> stringstream;  
typedef basic_stringstream<wchar_t> wstringstream;  
  
        // TEMPLATE FUNCTIONS  
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_stringbuf<CharType, Traits, Allocator>& _Left,  
        basic_stringbuf<CharType, Traits, Allocator>& _Right  
    );   
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_istringstream<CharType, Traits, Allocator>& _Left,  
        basic_istringstream<CharType, Traits, Allocator>& _Right  
    );  
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_ostringstream<CharType, Traits, Allocator>& _Left,  
        basic_ostringstream<CharType, Traits, Allocator>& _Right  
    );  
template<class CharType, class Traits, class Allocator>  
    void swap (  
        basic_stringstream<CharType, Traits, Allocator>& _Left,  
        basic_stringstream<CharType, Traits, Allocator>& _Right  
    );  
}  // namespace std  
  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`_Left`|Reference to an `sstream` object.|  
|`_Right`|Reference to an `sstream` object.|  
  
## 설명  
 Objects of type `char *` can use the functionality in [\<strstream\>](../standard-library/strstream.md) for streaming.  However, `<strstream>` is deprecated and the use of `<sstream>` is encouraged.  
  
### 형식 정의  
  
|||  
|-|-|  
|[istringstream](../Topic/istringstream.md)|Creates a type `basic_istringstream` specialized on a `char` template parameter.|  
|[ostringstream](../Topic/ostringstream.md)|Creates a type `basic_ostringstream` specialized on a `char` template parameter.|  
|[stringbuf](../Topic/stringbuf.md)|Creates a type `basic_stringbuf` specialized on a `char` template parameter.|  
|[stringstream](../Topic/stringstream.md)|Creates a type `basic_stringstream` specialized on a `char` template parameter.|  
|[wistringstream](../Topic/wistringstream.md)|Creates a type `basic_istringstream` specialized on a `wchar_t` template parameter.|  
|[wostringstream](../Topic/wostringstream.md)|Creates a type `basic_ostringstream` specialized on a `wchar_t` template parameter.|  
|[wstringbuf](../Topic/wstringbuf.md)|Creates a type `basic_stringbuf` specialized on a `wchar_t` template parameter.|  
|[wstringstream](../Topic/wstringstream.md)|Creates a type `basic_stringstream` specialized on a `wchar_t` template parameter.|  
  
### Manipulators  
  
|||  
|-|-|  
|[스왑](../Topic/%3Csstream%3E%20swap.md)|Exchanges the values between two `sstream` objects.|  
  
### 클래스  
  
|||  
|-|-|  
|[basic\_stringbuf](../standard-library/basic-stringbuf-class.md)|Describes a stream buffer that controls the transmission of elements of type **Elem**, whose character traits are determined by the class **Tr**, to and from a sequence of elements stored in an array object.|  
|[basic\_istringstream](../standard-library/basic-istringstream-class.md)|Describes an object that controls extraction of elements and encoded objects from a stream buffer of class [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>, with elements of type **Elem**, whose character traits are determined by the class **Tr**, and whose elements are allocated by an allocator of class `Alloc`.|  
|[basic\_ostringstream](../standard-library/basic-ostringstream-class.md)|Describes an object that controls insertion of elements and encoded objects into a stream buffer of class [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>, with elements of type **Elem**, whose character traits are determined by the class **Tr**, and whose elements are allocated by an allocator of class `Alloc`.|  
|[basic\_stringstream](../standard-library/basic-stringstream-class.md)|Describes an object that controls insertion and extraction of elements and encoded objects using a stream buffer of class [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\>, with elements of type **Elem**, whose character traits are determined by the class **Tr**, and whose elements are allocated by an allocator of class `Alloc`.|  
  
## 요구 사항  
  
-   **Header:** \<sstream\>  
  
-   **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)