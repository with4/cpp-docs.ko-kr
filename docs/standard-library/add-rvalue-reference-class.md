---
title: "add_rvalue_reference 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "type_traits/std::add_rvalue_reference"
  - "std::add_rvalue_reference"
  - "add_rvalue_reference"
  - "std.add_rvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_rvalue_reference 클래스"
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# add_rvalue_reference 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식인 경우는 개체 또는 함수 템플릿 매개 변수의 rvalue 참조 형식을 만듭니다. 그렇지 않으면 참조 축소의 의미 체계 때문에 형식이 템플릿 매개 변수와 동일 합니다.  
  
## 구문  
  
```cpp  
template<class T>  
    struct add_rvalue_reference;  
  
template<class T>  
    using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;  
```  
  
#### 매개 변수  
 T  
 수정할 형식입니다.  
  
## 설명  
 `add_rvalue_reference` 클래스에 명명 된 멤버가 `type`, 템플릿 매개 변수를 rvalue 참조의 형식에 대 한 별칭인 `T`합니다. 참조 축소의 의미 체계 의미를 개체가 아닌 및 비 함수 형식에 대 한 `T`, `T&&` 는 `T`합니다. 예를 들어, `T` lvalue 참조 형식으로  `add_rvalue_reference<T>::type` lvalue 참조 형식 rvalue 참조입니다.  
  
 편의 위해 \< type\_traits \> 도우미 템플릿으로 정의 `add_rvalue_reference_t`, 하는 별칭의 `type` 소속 `add_rvalue_reference`합니다.  
  
## 예제  
 이 코드 예제는 static\_assert rvalue 참조 형식을 사용 하 여 만들어지는 방법을 표시를 사용 하 여 `add_rvalue_reference` 및 `add_rvalue_reference_t`, 방법과의 결과 `add_rvalue_reference` lvalue 참조에 형식이 rvalue 참조는 없지만 lvalue 참조 형식으로 축소 합니다.  
  
```cpp  
// ex_add_rvalue_reference.cpp  
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp  
#include <type_traits>   
#include <iostream>   
#include <string>  
  
using namespace std;  
int main()  
{  
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,   
        "Expected add_rvalue_reference_t<string> to be string&&");  
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,   
        "Expected add_rvalue_reference_t<string*> to be string*&&");  
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,   
        "Expected add_rvalue_reference_t<string&> to be string&");  
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,   
        "Expected add_rvalue_reference_t<string&&> to be string&&");  
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;  
    return 0;  
}  
  
/*Output:  
All static_assert tests of add_rvalue_reference passed.  
*/  
```  
  
## 요구 사항  
 헤더: \<type\_traits\> 네임스페이스: std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [add\_lvalue\_reference 클래스](../standard-library/add-lvalue-reference-class.md)   
 [is\_rvalue\_reference 클래스](../standard-library/is-rvalue-reference-class.md)