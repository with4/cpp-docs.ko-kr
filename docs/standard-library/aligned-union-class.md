---
title: "aligned_union 클래스 | Microsoft Docs"
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
  - "aligned_union"
  - "std.aligned_union"
  - "std::aligned_union"
  - "type_traits/std::aligned_union"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_union"
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
caps.latest.revision: 10
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# aligned_union 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

공용 구조체 형식 및 필요한 크기를 저장 하는 POD 형식 충분 하 고 적절 하 게 정렬 된를 제공 합니다.  
  
## 구문  
  
```  
template <std::size_t Len, class... Types>  
    struct aligned_union;  
  
template <std::size_t Len, class... Types>  
    using aligned_union_t = typename aligned_union<Len, Types...>::type;  
```  
  
#### 매개 변수  
 `Len`  
 공용 구조체에서 가장 큰 형식의 맞춤 값입니다.  
  
 `Types`  
 기본 공용 구조체의 고유 형식입니다.  
  
## 설명  
 템플릿 클래스를 사용 하 여 맞춤 및 공용 구조체 초기화 되지 않은 저장소에 저장 하는 데 필요한 크기를 가져올 수 있습니다. 멤버 typedef `type` POD 이름 입력에 나열 된 모든 형식의 저장소에 대 한 적합 한 `Types`;의 최소 크기는 `Len`합니다. 정적 멤버 `alignment_value` 형식의 `std::size_t` 에 나열 된 모든 형식에 필요한 엄격한 맞춤 포함 `Types`합니다.  
  
## 예제  
 다음 예제를 사용 하는 방법을 보여 줍니다 `aligned_union` 공용 구조체를 배치 하는 정렬 된 스택 버퍼를 할당할 수 있습니다.  
  
```  
// std__type_traits__aligned_union.cpp  
#include <iostream>  
#include <type_traits>  
  
union U_type  
{  
    int i;  
    float f;  
    double d;  
    U_type(float e) : f(e) {}  
};  
  
typedef std::aligned_union<16, int, float, double>::type aligned_U_type;  
  
int main()  
{  
    // allocate memory for a U_type aligned on a 16-byte boundary  
    aligned_U_type au;  
    // do placement new in the aligned memory on the stack  
    U_type* u = new (&au) U_type(1.0f);  
    if (nullptr != u)  
    {  
        std::cout << "value of u->i is " << u->i << std::endl;  
        // must clean up placement objects manually!  
        u->~U_type();  
    }  
}  
```  
  
```Output  
값이-> i는 1065353216  
```  
  
## 요구 사항  
 **헤더:** \<type\_traits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [alignment\_of 클래스](../standard-library/alignment-of-class.md)