---
title: "응용 프로그램과 DLL의 차이점 | Microsoft Docs"
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
  - "응용 프로그램[C++], DLL과 비교"
  - "DLL[C++], 응용 프로그램과 비교"
  - "실행 파일[C++], DLL과 응용 프로그램 비교"
ms.assetid: 8f271523-d8d0-4ad1-84d2-0c5645d7fd5b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 응용 프로그램과 DLL의 차이점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL과 응용 프로그램은 모두 실행 가능한 프로그램 모듈이지만 다른 점이 몇 가지 있습니다.  최종 사용자에게 있어 가장 분명한 차이점은 DLL의 경우 사용자가 직접 실행할 수 있는 프로그램이 아니라는 점입니다.  또한 시스템 관점에서 볼 때 응용 프로그램과 DLL 사이에는 다음과 같은 두 개의 기본적인 차이점이 있습니다.  
  
-   응용 프로그램의 경우에는 시스템에서 해당 인스턴스가 동시에 여러 개 실행될 수 있지만 DLL의 경우에는 하나의 인스턴스만 실행됩니다.  
  
-   응용 프로그램에는 스택, 전역 메모리, 파일 핸들 및 메시지 큐 등이 포함될 수 있지만 DLL은 그렇지 않습니다.  
  
## 수행할 작업  
  
-   [DLL에서 내보내기](../build/exporting-from-a-dll.md)  
  
-   [DLL에 실행 파일 링크](../build/linking-an-executable-to-a-dll.md)  
  
-   [DLL 초기화](../build/initializing-a-dll.md)  
  
## 추가 정보  
  
-   [DLL 사용의 장점](../build/advantages-of-using-dlls.md)  
  
-   [비 MFC DLL: 개요](../build/non-mfc-dlls-overview.md)  
  
-   [정적으로 MFC에 링크된 기본 DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크하는 기본 DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [확장 DLL: 개요](../build/extension-dlls-overview.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)