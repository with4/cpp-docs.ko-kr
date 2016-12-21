---
title: "naked(C++) | Microsoft Docs"
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
  - "naked_cpp"
  - "naked"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드[C++], naked"
  - "naked __declspec 키워드"
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# naked(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `naked` 특성으로 선언된 함수의 경우 컴파일러는 프롤로그 및 에필로그 코드가 없는 코드를 생성합니다.  이 기능을 이용하여 인라인 어셈블러 코드로 사용자 정의 프롤로그\/에필로그 코드 시퀀스를 작성할 수 있습니다.  naked 함수는 가상 장치 드라이버 작성에 특히 유용합니다.  이 `naked` 특성은 x86과 ARM에만 유효하며 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]에서 사용할 수 없습니다.  
  
## 구문  
  
```  
__declspec(naked) declarator  
```  
  
## 설명  
 `naked` 특성이 함수의 정의와만 관련이 있고 형식 수정자가 아니기 때문에 naked 함수는 확장된 특성 구문을 사용하고 [\_\_declspec](../cpp/declspec.md) 키워드를 사용해야 합니다.  
  
 컴파일러는 함수가 [\_\_forceinline](../misc/inline-inline-forceinline.md) 키워드로도 표시되는 경우에도 naked 특성으로 표시된 함수에 대해 인라인 함수를 생성할 수 없습니다.  
  
 컴파일러는 `naked` 특성이 비멤버 메서드의 정의가 아닌 다른 것에 적용되는 경우 오류를 발행합니다.  
  
## 예제  
 이 코드는 다음과 같이 `naked` 특성을 사용하는 함수를 정의합니다.  
  
```  
__declspec( naked ) int func( formal_parameters ) {}  
```  
  
 또는, 교대로:  
  
```  
#define Naked __declspec( naked )  
Naked int func( formal_parameters ) {}  
```  
  
 `naked` 특성은 함수의 프롤로그 및 에필로그 시퀀스에 사용되는 컴파일러 코드 생성에만 영향을 줍니다.  이러한 함수를 호출하기 위해 생성되는 코드에는 영향을 주지 않습니다.  따라서 `naked` 특성을 함수 형식의 일부로 간주하지 않으며, 함수 포인터는 `naked` 특성을 가질 수 없습니다.  또한 `naked` 특성은 데이터 정의에 적용될 수 없습니다.  예를 들어, 이 코드 샘플은 오류를 생성합니다.  
  
```  
__declspec( naked ) int i;       // Error--naked attribute not  
                                 // permitted on data declarations.  
```  
  
 `naked` 특성은 함수 정의에만 관련되며, 함수의 프로토타입에 지정될 수 없습니다.  예를 들어, 이 선언은 컴파일러 오류를 생성합니다.  
  
```  
__declspec( naked ) int func();  // Error--naked attribute not   
                                 // permitted on function declarations  
```  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [Naked 함수 호출](../cpp/naked-function-calls.md)