---
title: "도우미 함수 이해 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__delayLoadHelper 함수"
  - "__delayLoadHelper2 함수"
  - "지연 DLL 로드, 도우미 함수"
  - "delayhlp.cpp"
  - "delayimp.h"
  - "delayimp.lib"
  - "도우미 함수"
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 도우미 함수 이해
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링커가 지원하는 지연 로드를 위한 도우미 함수는 실제로 런타임에 DLL을 로드합니다.  Delayimp.lib에서 제공하는 도우미 함수를 사용하는 대신 사용자가 직접 도우미 함수를 작성하고 자신의 프로그램에 링크함으로써 도우미 함수의 동작을 사용자 지정할 수 있습니다.  도우미 함수 하나가 지연 로드된 DLL을 모두 지원합니다.  
  
 DLL이나 가져오기 이름에 따라 특정 처리를 수행하려는 경우 도우미 함수의 개인 버전을 제공할 수 있습니다.  
  
 도우미 함수는 다음 동작을 수행합니다.  
  
-   라이브러리에 대한 저장 핸들이 이미 로드되어 있는지 확인합니다.  
  
-   **LoadLibrary**를 호출하여 DLL을 로드합니다.  
  
-   **GetProcAddress**를 호출하여 프로시저의 주소를 가져옵니다.  
  
-   지연 가져오기 로드 썽크로 제어를 반환하여 현재 로드된 진입점을 호출합니다.  
  
 도우미 함수는 다음 동작이 수행될 때마다 프로그램의 알림 후크로 콜백할 수 있습니다.  
  
-   도우미 함수가 시작될 때  
  
-   도우미 함수에서 **LoadLibrary**가 호출되기 바로 전  
  
-   도우미 함수에서 **GetProcAddress**가 호출되기 바로 전  
  
-   도우미 함수에서 **LoadLibrary** 호출이 수행되지 못한 경우  
  
-   도우미 함수에서 **GetProcAddress** 호출이 수행되지 못한 경우  
  
-   도우미 함수가 처리를 완료한 후  
  
 이러한 후크 지점마다 지연 가져오기 로드 썽크로 제어를 반환하는 것을 제외하고 어떤 식으로든 도우미 루틴의 정상적인 처리를 변경하게 될 값을 반환할 수 있습니다.  
  
 기본 도우미 코드는 Delayhlp.cpp 및 Delayimp.h\(vc\\include\)에 있으며 Delayimp.lib\(vc\\lib\)에서 컴파일됩니다.  사용자가 직접 도우미 함수를 작성하지 않는 경우에는 컴파일할 때 이 라이브러리를 포함시켜야 합니다.  
  
 다음 항목에서는 도우미 함수에 대해 설명합니다.  
  
-   [Visual C\+\+ 6.0 이후 DLL 지연 로드 도우미 함수의 변경 내용](../../build/reference/changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)  
  
-   [호출 규칙, 매개 변수, 반환 형식](../../build/reference/calling-conventions-parameters-and-return-type.md)  
  
-   [구조체 및 상수 정의](../../build/reference/structure-and-constant-definitions.md)  
  
-   [필요한 값 계산](../../build/reference/calculating-necessary-values.md)  
  
-   [지연 로드된 DLL 언로드](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
## 참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)