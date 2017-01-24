---
title: "exception 클래스 | Microsoft Docs"
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
  - "std.exception"
  - "exception"
  - "std::exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exception 클래스"
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# exception 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 클래스는 특정 식과 표준 C\+\+라이브러리로, 나타난 모든 예외에 대한 기본 클래스로 사용됩니다.  
  
## 구문  
  
```  
class exception {  
public:  
    exception();  
    exception(const char * const &message);  
    exception(const char * const &message, int);  
    exception(const exception &right);  
    exception& operator=(const exception &right);  
    virtual ~exception();  
    virtual const char *what() const;  
};  
```  
  
## 설명  
 Specifically, this base class is the root of the standard exception classes defined in [\<stdexcept\>](../standard-library/stdexcept.md).  The C string value returned by `what` is left unspecified by the default constructor, but may be defined by the constructors for certain derived classes as an implementation\-defined C string.  None of the member functions throw any exceptions.  
  
 The `int` parameter allows you to specify that no memory should be allocated.  The value of the `int` is ignored.  
  
> [!NOTE]
>  The constructors `exception(const char * const &message)` and `exception(const char * const &message, int)` are Microsoft extensions to the Standard C\+\+ Library.  
  
## 예제  
 For examples of the use of the standard exception classes that inherit from the `exception` class, see any of the classes defined in [\<stdexcept\>](../standard-library/stdexcept.md).  
  
## 요구 사항  
 **Header:** \<exception\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)