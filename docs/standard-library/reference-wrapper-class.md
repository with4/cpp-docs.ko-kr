---
title: "reference_wrapper 클래스 | Microsoft Docs"
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
  - "std.tr1.reference_wrapper"
  - "tr1.reference_wrapper"
  - "reference_wrapper"
  - "tr1::reference_wrapper"
  - "xrefwrap/std::tr1::reference_wrapper"
  - "std::tr1::reference_wrapper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reference_wrapper 클래스"
  - "reference_wrapper 클래스[TR1]"
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
caps.latest.revision: 21
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# reference_wrapper 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

참조를 래핑합니다.  
  
## 구문  
  
```  
template<class Ty>  
    class reference_wrapper  
    : public unary_function<T1, Ret>        // see below  
    : public binary_function<T1, T2, Ret>   // see below  
    {  
public:  
    typedef Ty type;  
    typedef T0 result_type;                 // see below  
  
    reference_wrapper(Ty&);  
  
    Ty& get() const;  
    operator Ty&() const;  
    template<class T1, class T2, ..., class TN>  
        typename result_of<T(T1, T2, ..., TN)>::type  
        operator()(T1&, T2&, ..., TN&);  
  
private:  
    Ty *ptr; // exposition only  
    };  
```  
  
## 설명  
 `reference_wrapper<Ty>`는 복사를 통해 생성 및 할당할 수 있으며 `Ty` 형식의 개체를 가리키는 포인터를 보유합니다.  
  
 `reference_wrapper<Ty>` 특수화는 `Ty` 형식이 다음과 같은 경우에만 `std::unary_function<T1, Ret>`에서 파생되어 중첩 형식 `result_type`을 `Ret`의 동의어로 정의하고 중첩 형식 `argument_type`을 `T1`의 동의어로 정의합니다.  
  
 `T1` 형식의 인수 하나를 사용하고 `Ret`를 반환하는 함수 형식 또는 함수 형식에 대한 포인터 또는  
  
 멤버 함수 `Ret T::f() cv`에 대한 포인터. 여기서 `cv`는 멤버 함수의 cv 한정자를 나타내고, `T1` 형식은 `cv` `T*`입니다. 또는  
  
 `unary_function<T1, Ret>`에서 파생된 클래스 형식.  
  
 `reference_wrapper<Ty>` 특수화는 `Ty` 형식이 다음과 같은 경우에만 `std::binary_function<T1, T2, Ret>`에서 파생되어 중첩 형식 `result_type`을 `Ret`의 동의어로 정의하고, 중첩 형식 `first_argument_type`을 `T1`의 동의어로 정의하고, 중첩 형식 `second_argument_type`을 `T2`의 동의어로 정의합니다.  
  
 `T1` 및 `T2` 형식의 인수 두 개를 사용하고 `Ret`를 반환하는 함수 형식 또는 함수 형식에 대한 포인터 또는  
  
 멤버 함수 `Ret T::f(T2) cv`에 대한 포인터. 여기서 `cv`는 멤버 함수의 cv 한정자를 나타내고, `T1` 형식은 `cv` `T*`입니다. 또는  
  
 `binary_function<T1, T2, Ret>`에서 파생된 클래스 형식.  
  
### 생성자  
  
|||  
|-|-|  
|[reference\_wrapper::reference\_wrapper](../Topic/reference_wrapper::reference_wrapper.md)|`reference_wrapper`를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[reference\_wrapper::result\_type](../Topic/reference_wrapper::result_type.md)|래핑된 참조의 약한 결과 형식입니다.|  
|[reference\_wrapper::type](../Topic/reference_wrapper::type.md)|래핑된 참조 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[reference\_wrapper::get](../Topic/reference_wrapper::get.md)|래핑된 참조를 가져옵니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[reference\_wrapper::operator Ty&](../Topic/reference_wrapper::operator%20Ty&.md)|래핑된 참조에 대한 포인터를 가져옵니다.|  
|[reference\_wrapper::operator\(\)](../Topic/reference_wrapper::operator\(\).md)|래핑된 참조를 호출합니다.|  
  
## 요구 사항  
 **헤더:** \<functional\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [cref 함수](../Topic/cref%20Function.md)   
 [ref 함수](../Topic/ref%20Function.md)