---
title: "type_info 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "type_info"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "type_info 클래스"
  - "type_info 클래스"
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# type_info 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**type\_info** 클래스는 컴파일러가 프로그램 안에 생성하는 형식 정보에 대해 설명합니다.  이 클래스의 개체는 형식의 이름에 대한 포인터를 효과적으로 저장합니다.  **type\_info** 클래스는 두 형식의 동일성이나 정렬 순서를 비교하는 데 적합한 인코딩 값을 저장하기도 합니다.  형식의 인코딩 규칙 및 정렬 시퀀스는 지정되지 않으며 프로그램 간에 다를 수 있습니다.  
  
 **type\_info** 클래스를 사용하려면 \<`typeinfo>` 헤더 파일이 포함되어야 합니다.  **type\_info** 클래스의 인터페이스는 다음과 같습니다.  
  
```  
class type_info {  
public:  
    virtual ~type_info();  
    size_t hash_code() const  
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;  
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;  
    _CRTIMP_PURE int before(const type_info& rhs) const;  
    _CRTIMP_PURE const char* name() const;  
    _CRTIMP_PURE const char* raw_name() const;  
};  
```  
  
 **type\_info** 클래스에 전용 복사 생성자가 하나만 있으므로 클래스의 개체를 직접 인스턴스화할 수 없습니다.  **type\_info** 개체\(임시\)를 생성하는 유일한 방법은 [typeid](../cpp/typeid-operator.md) 연산자를 사용하는 것입니다.  대입 연산자도 전용이므로 **type\_info** 클래스의 개체를 복사하거나 할당할 수 없습니다.  
  
 **type\_info::hash\_code**는 **typeinfo** 형식의 값을 인덱스 값의 분포에 매핑하는 데 적합한 해시 함수를 정의합니다.  
  
 `==` 및 `!=` 연산자를 사용하여 **type\_info** 개체의 같음과 다름을 각각 비교할 수 있습니다.  
  
 형식의 정렬 순서와 상속 관계 간에 링크가 없습니다.  **type\_info::before** 멤버 함수를 사용하여 형식의 정렬 시퀀스를 결정하십시오.  다른 프로그램에서 또는 같은 프로그램의 다른 실행에서 **type\_info::before**가 같은 결과를 낸다는 보장은 없습니다.  이런 면에서 **type\_info::before**는 address\-of**\(&\)** 연산자와 비슷합니다.  
  
 **type\_info::name** 멤버 함수는 사용자가 읽을 수 있는 형식 이름을 나타내고 null로 끝나는 문자열에 **const char\***을 반환합니다.  가리키는 메모리는 캐시되며 직접 할당 해지되면 안 됩니다.  
  
 **type\_info::raw\_name** 멤버 함수는 데코레이팅된 개체 형식 이름을 나타내며 null로 끝나는 문자열에 **const char\***을 반환합니다.  공간을 절약하기 위해 이름은 실제로 데코레이팅된 형식으로 저장됩니다.  따라서 이 함수는 이름의 데코레이팅을 취소할 필요가 없으므로 **type\_info::name**보다 빠릅니다.  **type\_info::raw\_name** 함수가 반환하는 문자열은 비교 연산에 유용하지만 읽을 수 없습니다.  사용자가 읽을 수 있는 문자열이 필요할 경우 **type\_info::name** 함수를 대신 사용하십시오.  
  
 [\/GR\(런타임 형식 정보 사용\)](../build/reference/gr-enable-run-time-type-information.md) 컴파일러 옵션이 지정된 경우에만 다형 클래스의 형식 정보가 생성됩니다.  
  
## 참고 항목  
 [런타임 형식 정보](../cpp/run-time-type-information.md)