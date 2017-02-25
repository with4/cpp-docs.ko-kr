---
title: "bad_weak_ptr 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "memory/std::tr1::bad_weak_ptr"
  - "std::tr1::bad_weak_ptr"
  - "bad_weak_ptr"
  - "tr1::bad_weak_ptr"
  - "tr1.bad_weak_ptr"
  - "std.tr1.bad_weak_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_weak_ptr 클래스"
  - "bad_weak_ptr 클래스[TR1]"
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# bad_weak_ptr 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

불량 weak\_ptr 예외를 보고합니다.  
  
## 구문  
  
```  
class bad_weak_ptr  
    : public std::exception {  
public:  
    bad_weak_ptr();  
    const char *what() throw();  
    };  
```  
  
## 설명  
 이 클래스는 [weak\_ptr 클래스](../standard-library/weak-ptr-class.md) 형식의 인수를 사용하는 [shared\_ptr 클래스](../standard-library/shared-ptr-class.md) 생성자에서 발생할 수 있는 예외를 설명합니다.  멤버 함수 `what`에서 `"bad_weak_ptr"`을 반환합니다.  
  
## 예제  
  
```  
// std_tr1__memory__bad_weak_ptr.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::weak_ptr<int> wp;   
  
     {   
    std::shared_ptr<int> sp(new int);   
    wp = sp;   
     }   
  
    try   
        {   
        std::shared_ptr<int> sp1(wp); // weak_ptr has expired   
        }   
    catch (const std::bad_weak_ptr&)   
        {   
        std::cout << "bad weak pointer" << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
  **잘못된 약한 포인터**   
## 요구 사항  
 **헤더:** \<memory\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [weak\_ptr 클래스](../standard-library/weak-ptr-class.md)