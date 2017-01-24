---
title: "is_pod 클래스 | Microsoft Docs"
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
  - "std.tr1.is_pod"
  - "is_pod"
  - "std::tr1::is_pod"
  - "std.is_pod"
  - "std::is_pod"
  - "type_traits/std::is_pod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_pod 클래스[TR1]"
  - "is_pod"
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_pod 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식이 POD인지 테스트합니다.  
  
## 구문  
  
```  
template<class Ty>  
    struct is_pod;  
```  
  
#### 매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## 설명  
 `Ty` 형식이 POD\(Plain Old Data\)이면 `is_pod<Ty>::value`가 `true`입니다.  그렇지 않으면 `false`입니다.  
  
 산술 형식, 열거형 형식, 포인터 형식 및 멤버 형식에 대한 포인터는 POD입니다.  
  
 POD 형식의 cv 한정된 버전 자체도 POD 형식입니다.  
  
 POD 배열 자체도 POD입니다.  
  
 다음 조건을 충족하는 경우 해당 비정적 데이터 멤버가 모두 POD인 구조체 또는 공용 구조체 자체도 POD입니다.  
  
-   사용자가 선언한 생성자 없음  
  
-   전용 또는 보호된 비정적 데이터 멤버 없음  
  
-   기본 클래스 없음  
  
-   가상 함수 없음  
  
-   참조 형식의 비정적 데이터 멤버 없음  
  
-   사용자 정의 복사 할당 연산자 없음  
  
-   사용자 정의 소멸자 없음  
  
 따라서 POD 구조체 및 배열을 포함하는 POD 구조체 및 배열을 재귀적으로 빌드할 수 있습니다.  
  
## 예제  
  
```  
// std_tr1__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct throws   
    {   
    throws() throw(int)   
        {   
        }   
  
    throws(const throws&) throw(int)   
        {   
        }   
  
    throws& operator=(const throws&) throw(int)   
        {   
        }   
  
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_pod\<trivial\> \=\= true**  
**is\_pod\<int\> \=\= true**  
**is\_pod\<throws\> \=\= false**   
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)