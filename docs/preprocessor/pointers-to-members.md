---
title: "pointers_to_members | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pointers_to_members_CPP"
  - "vc-pragma.pointers_to_members"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클래스 멤버, 포인터"
  - "멤버, 포인터"
  - "pointers_to_members pragma"
  - "pragma, pointers_to_members"
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# pointers_to_members
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 연결된 클래스 정의 앞에 클래스 멤버의 포인터를 선언할 수 있으며 이 포인터를 사용하여 포인터 크기 및 포인터를 해석하는 데 필요한 코드를 제어하는지 여부를 지정합니다.  
  
## 구문  
  
```  
  
#pragma pointers_to_members( pointer-declaration, [most-general-representation] )  
```  
  
## 설명  
 [\/vmx](../build/reference/vmb-vmg-representation-method.md) 컴파일러 옵션 또는 [상속 키워드](../cpp/inheritance-keywords.md)를 사용하는 대신 **pointers\_to\_members** pragma를 소스 파일에 사용할 수 있습니다.  
  
 *pointer\-declaration* 인수는 멤버의 포인터를 연결된 함수 정의 앞에 선언했는지 뒤에 선언했는지 지정합니다.  *pointer\-declaration* 인수는 다음 두 가지 기호 중 하나입니다.  
  
|인수|설명|  
|--------|--------|  
|**full\_generality**|안전하며 때로 최적이 아닌 코드를 생성합니다.  연결된 클래스 정의 앞에 멤버의 포인터가 선언될 경우 **full\_generality**를 사용합니다.  이 인수는 *most\-general\-representation* 인수로 지정된 포인터 표현을 항상 사용합니다.  \/vmg와 같습니다.|  
|**best\_case**|멤버의 모든 포인터에 대해 최상의 표현을 사용하는 최적의 안전한 코드를 생성합니다.  클래스의 멤버에 대한 포인터를 선언하기 전에 클래스를 정의해야 합니다.  기본값은 **best\_case**입니다.|  
  
 *most\-general\-representation* 인수는 컴파일러가 변환 단위로 클래스 멤버의 포인터를 참조하기 위해 안전하게 사용할 수 있는 최소 포인터 표현을 지정합니다.  인수는 다음 중 하나가 될 수 있습니다.  
  
|인수|설명|  
|--------|--------|  
|**single\_inheritance**|가장 일반적인 표현은 멤버 함수 포인터인 단일 상속입니다.  멤버 포인터가 선언되는 클래스 정의의 상속 모델이 다중 또는 가상일 경우 오류를 생성합니다.|  
|**multiple\_inheritance**|가장 일반적인 표현은 멤버 함수 포인터인 다중 상속입니다.  멤버 포인터가 선언되는 클래스 정의의 상속 모델이 가상일 경우 오류를 생성합니다.|  
|**virtual\_inheritance**|가장 일반적인 표현은 멤버 함수 포인터인 가상 상속입니다.  오류를 생성하지 않습니다.  **\#pragma pointers\_to\_members\(full\_generality\)**가 사용되는 경우 기본 인수입니다.|  
  
> [!CAUTION]
>  영향을 줄 소스 코드 파일에 한해 `#include` 지시문 뒤에 `pointers_to_members` pragma를 배치해야 합니다.  그러면 pragma가 다른 파일에 영향을 줄 위험이 주고 잘못해서 같은 변수, 함수 또는 클래스 이름에 대해 여러 정의를 지정하는 위험이 줄어듭니다.  
  
## 예제  
  
```  
//   Specify single-inheritance only  
#pragma pointers_to_members( full_generality, single_inheritance )  
```  
  
## C\+\+ 전용 종료  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)