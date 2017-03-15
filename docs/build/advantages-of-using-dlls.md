---
title: "DLL 사용의 장점 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL[C++], 이점"
  - "동적 링크[C++]"
  - "동적 로드 링크[C++]"
  - "링크[C++], 동적과 정적 비교"
  - "링크[C++], 동적과 정적 비교"
ms.assetid: 8956c8ee-e7b3-446f-a0c6-462381747690
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# DLL 사용의 장점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

동적 링크에는 다음과 같은 장점이 있습니다.  
  
-   메모리를 절약하고 스와핑을 줄입니다.  여러 프로세스가 메모리에 있는 하나의 DLL 복사본을 공유하여 하나의 DLL을 동시에 사용할 수 있습니다.  반면, 정적 연결 라이브러리를 사용하여 빌드된 응용 프로그램의 경우 Windows는 각 응용 프로그램에 대해 하나의 라이브러리 코드 복사본을 메모리에 로드해야 합니다.  
  
-   디스크 공간을 절약합니다.  여러 응용 프로그램이 디스크에 있는 하나의 DLL 복사본을 공유할 수 있습니다.  반면, 정적 연결 라이브러리를 사용하여 빌드된 응용 프로그램의 경우에는 각 응용 프로그램마다 별도의 복사본으로서 실행 가능한 이미지에 링크되는 라이브러리 코드가 있습니다.  
  
-   DLL을 보다 쉽게 업그레이드할 수 있습니다.  DLL의 함수가 변경되어도 이 함수의 인수 및 반환 값이 변경되지 않았으면 그 함수를 사용하는 응용 프로그램은 다시 컴파일하거나 링크할 필요가 없습니다.  반면, 정적으로 링크되는 개체 코드의 경우에는 함수가 변경되면 응용 프로그램을 다시 링크시켜야 합니다.  
  
-   출시 후 지원이 가능합니다.  예를 들어, 응용 프로그램을 출시할 때 사용할 수 없었던 디스플레이 기능을 지원하도록 디스플레이 드라이버 DLL을 수정할 수 있습니다.  
  
-   언어 형식이 다른 여러 프로그램을 지원합니다.  서로 다른 프로그래밍 언어로 작성된 프로그램인 경우에도 함수의 호출 규칙을 따르기만 하면 여러 프로그램에서 동일한 DLL 함수를 호출할 수 있습니다.  이 경우 각 프로그램과 DLL 함수는 여러 가지 면\(스택에 해당 함수의 인수가 들어가는 순서, 스택을 정리하는 것이 함수인지 응용 프로그램인지의 여부 및 인수가 레지스터에 전달되는지의 여부\)에서 호환될 수 있어야 합니다.  
  
-   MFC 라이브러리 클래스를 확장하기 위한 메커니즘을 제공합니다.  기존의 MFC 클래스에서 클래스를 파생시켜 MFC 응용 프로그램에서 사용할 수 있도록MFC 확장 DLL에 포함시킬 수 있습니다.  
  
-   국가별 버전을 쉽게 만들 수 있습니다.  리소스를 DLL에 포함시키면 응용 프로그램의 국가별 버전을 훨씬 쉽게 만들 수 있습니다.  응용 프로그램의 각 언어 버전에서 사용되는 문자열을 별도의 리소스 DLL에 포함시키고, 각 언어 버전에 따라 적절한 리소스가 로드되도록 하면 됩니다.  
  
 DLL을 사용하면 응용 프로그램이 비독립적이라는 단점이 있습니다. 즉, 응용 프로그램에는 별도의 DLL 모듈이 있어야 합니다.  
  
## 수행할 작업  
  
-   [DLL에서 내보내기](../build/exporting-from-a-dll.md)  
  
-   [DLL에 실행 파일 링크](../build/linking-an-executable-to-a-dll.md)  
  
-   [DLL 초기화](../build/initializing-a-dll.md)  
  
## 추가 정보  
  
-   [비 MFC DLL: 개요](../build/non-mfc-dlls-overview.md)  
  
-   [정적으로 MFC에 링크된 기본 DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크하는 기본 DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [확장 DLL: 개요](../build/extension-dlls-overview.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)