---
title: "다중 스레드 프로그램 컴파일 및 링크 | Microsoft Docs"
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
  - "다중 스레드 프로그램 컴파일"
  - "소스 코드 컴파일[C++], 다중 스레드 프로그램"
  - "링크[C++], 다중 스레드 프로그램"
  - "다중 스레딩[C++], 컴파일된 프로그램"
  - "다중 스레딩[C++], 프로그램 링크"
  - "스레딩[C++], 컴파일된 프로그램"
  - "스레딩[C++], 프로그램 링크"
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 다중 스레드 프로그램 컴파일 및 링크
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bounce.c 프로그램은 [샘플 다중 스레드 C 프로그램](../../parallel/sample-multithread-c-program.md)에서 설명합니다.  
  
 프로그램은 기본적으로 다중 스레드로 컴파일됩니다.  
  
#### 개발 환경 내에서 Bounce.c 다중 스레드 프로그램을 컴파일하고 링크하려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  **프로젝트 형식** 창에서 **Win32**를 클릭합니다.  
  
3.  **템플릿** 창에서 **Win32 콘솔 응용 프로그램**을 클릭한 다음 프로젝트의 이름을 지정합니다.  
  
4.  C 소스 코드를 포함하는 파일을 프로젝트에 추가합니다.  
  
5.  **빌드** 메뉴에서 **빌드** 명령을 클릭하여 프로젝트를 빌드합니다.  
  
#### 명령줄에서 Bounce.c 다중 스레드 프로그램을 컴파일하고 링크하려면  
  
1.  다음 명령을 사용하여 프로그램을 컴파일하고 링크합니다.  
  
    ```  
    CL BOUNCE.C  
    ```  
  
## 참고 항목  
 [C 및 Wind32를 사용한 다중 스레딩](../../parallel/multithreading-with-c-and-win32.md)