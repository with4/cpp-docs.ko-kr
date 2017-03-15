---
title: "Windows에서 DLL을 찾는 데 사용되는 검색 경로 | Microsoft Docs"
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
  - "DLL[C++], Windows 검색 경로"
  - "DLL 찾기"
  - "알려진 DLL 검색[C++]"
  - "DLL 찾기"
  - "검색 경로[C++]"
  - "검색[C++], DLL"
  - "Windows[C++], DLL 검색 경로"
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Windows에서 DLL을 찾는 데 사용되는 검색 경로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

암시적 링크와 명시적 링크의 경우 모두 Windows는 Kernel32.dll 및 User32.dll과 같이 "알려진 DLL"을 먼저 검색합니다.  그런 다음 아래 순서에 따라 DLL을 검색합니다.  
  
1.  현재 프로세스의 실행 모듈이 있는 디렉터리  
  
2.  현재 디렉터리  
  
3.  Windows 시스템 디렉터리.  **GetSystemDirectory** 함수가 이 디렉터리의 경로를 검색합니다.  
  
4.  Windows 디렉터리.  **GetWindowsDirectory** 함수가 이 디렉터리의 경로를 검색합니다.  
  
5.  PATH 환경 변수에 나열된 디렉터리  
  
    > [!NOTE]
    >  LIBPATH 환경 변수는 사용되지 않습니다.  
  
## 수행할 작업  
  
-   [암시적 링크](../build/linking-implicitly.md)  
  
-   [명시적 링크](../build/linking-explicitly.md)  
  
-   [사용할 링크 방법 결정](../build/determining-which-linking-method-to-use.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)