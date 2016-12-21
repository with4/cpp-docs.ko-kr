---
title: "#undef 지시문 (C/C++) | Microsoft Docs"
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
  - "#undef"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#undef 지시문"
  - "전처리기, 지시문"
  - "undef 지시문(#undef)"
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #undef 지시문 (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

전에 `#define`으로 만든 이름을 제거\(정의 해제\)합니다.  
  
## 구문  
  
```  
  
#undef   
identifier  
  
```  
  
## 설명  
 `#undef` 지시문은 *identifier*의 현재 정의를 제거합니다.  그 결과 전처리기가 이후에 나오는 *identifier*를 무시합니다.  `#undef`를 사용하여 매크로 정의를 제거하려면 매크로 *identifier*만 제공하고 매개 변수 목록은 제공하지 마십시오.  
  
 이전의 정의가 없는 식별자에 `#undef` 지시문을 적용할 수도 있습니다.  그러면 식별자가 정의되지 않습니다.  `#undef` 문에서 매크로가 바뀌지 않습니다.  
  
 대개 `#undef` 지시문은 `#define` 지시문과 쌍을 이루어 식별자가 특별한 의미를 갖는 소스 프로그램에서 영역을 만듭니다.  예를 들어, 소스 프로그램의 특정한 함수가 매니페스트 상수를 사용하여 프로그램의 나머지 부분에 영향을 주지 않는 환경 관련 값을 정의할 수 있습니다.  또한 `#undef` 지시문은 `#if` 지시문과 함께 사용되어 소스 프로그램의 조건부 컴파일을 제어합니다.  자세한 내용은 [\#if, \#elif, \#else 및 \#endif 지시문](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)을 참조하십시오.  
  
 다음 예제에서 `#undef` 지시문이 기호 상수 및 매크로의 정의를 제거합니다.  매크로의 식별자만 제공됩니다.  
  
```  
#define WIDTH 80  
#define ADD( X, Y ) ((X) + (Y))  
.  
.  
.  
#undef WIDTH  
#undef ADD  
```  
  
 **Microsoft 전용**  
  
 명령줄에서 \/U 옵션 뒤에 정의 해제할 매크로 이름을 입력하여 매크로 정의를 해제할 수 있습니다.  이 명령을 실행할 경우 파일 시작 부분의 `#undef` *macro\-name* 문 시퀀스와 같은 효과가 있습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)