---
title: "/volatile(volatile 키워드 해석) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/volatile:iso"
  - "/volatile:ms"
  - "/volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/volatile 컴파일러 옵션"
  - "/volatile 컴파일러 옵션[C++]"
  - "volatile 컴파일러 옵션"
  - "-volatile 컴파일러 옵션"
  - "volatile 컴파일러 옵션[C++]"
  - "-volatile 컴파일러 옵션[C++]"
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# /volatile(volatile 키워드 해석)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[volatile](../../cpp/volatile-cpp.md) 키워드를 해석할 방법을 지정합니다.  
  
## 구문  
  
```  
/volatile:{iso|ms}  
```  
  
## 인수  
 **\/volatile:iso**  
 ISO 표준 C\+\+ 언어에서 정의한 엄격한 `volatile` 의미 체계를 선택합니다.  volatile 액세스에 acquire\/release 의미 체계가 보장되지 않습니다.  컴파일러가 ARM을 대상으로 하는 경우 `volatile`의 기본 해석입니다.  
  
 **\/volatile:ms**  
 ISO 표준 C\+\+ 언어 이상으로 Memory Ordering 보장을 추가하는 Microsoft 확장 `volatile` 의미 체계를 선택합니다.  volatile 액세스에 acquire\/release 의미 체계가 보장됩니다.  그러나 이 옵션은 컴파일러가 하드웨어 메모리 장애를 생성하도록 강제로 지정할 수 있습니다. 이러한 장애가 발생하면 ARM 및 기타 메모리 순서가 엄격하게 적용되지 않는 아키텍처에 상당한 오버헤드를 추가할 수 있습니다.  컴파일러가 ARM을 제외한 모든 플랫폼을 대상으로 하는 경우 `volatile`의 기본 해석입니다.  
  
## 설명  
 스레드 간에 공유되는 메모리를 처리할 때 명시적 동기화 기본 형식 및 컴파일러 내장 함수와 **\/volatile:iso**를 함께 사용하는 것이 좋습니다.  자세한 내용은 [volatile](../../cpp/volatile-cpp.md)을 참조하십시오.  
  
 기존 코드를 이식하거나 프로젝트 중간에 이 옵션을 변경할 경우에는 의미 체계의 다른 점으로 인해 영향을 받는 코드 위치를 식별할 수 있도록 [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) 경고를 사용하도록 설정하는 것이 도움이 될 수 있습니다.  
  
 이 옵션을 제어하는 데 `#pragma`와 동일한 옵션은 없습니다.  
  
### Visual Studio에서 \/volatile 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션** 상자에서 `/volatile:iso` 또는 `/volatile:ms`를 추가합니다.  
  
## 참고 항목  
 [volatile](../../cpp/volatile-cpp.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)