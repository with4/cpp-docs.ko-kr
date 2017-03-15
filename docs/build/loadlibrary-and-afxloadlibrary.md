---
title: "LoadLibrary 및 AfxLoadLibrary | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LoadLibrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxLoadLibrary 메서드"
  - "DLL[C++], AfxLoadLibrary"
  - "DLL[C++], LoadLibrary"
  - "명시적 링크[C++]"
  - "LoadLibrary 메서드"
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# LoadLibrary 및 AfxLoadLibrary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로세스는 [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187) 또는 [AfxLoadLibrary](../Topic/AfxLoadLibrary.md)를 호출하여 DLL에 명시적으로 링크합니다.  DLL 링크에 성공한 경우 이 함수는 지정된 DLL을 호출 프로세스의 주소 공간에 매핑하고 명시적 링크의 다른 함수\(`GetProcAddress` 및 `FreeLibrary` 등\)와 함께 사용될 수 있는 핸들을 해당 DLL에 반환합니다.  
  
 `LoadLibrary`는 암시적 링크에 사용되는 것과 동일한 검색 시퀀스를 사용하여 DLL을 찾습니다.  시스템에서 DLL을 찾을 수 없거나 진입점 함수가 FALSE를 반환하는 경우에는 `LoadLibrary`가 NULL을 반환합니다.  또한 `LoadLibrary` 호출이 이미 매핑된 DLL 모듈을 호출 프로세스의 주소 공간에 지정하는 경우, 이 함수는 단순히 해당 DLL의 핸들을 반환하고 해당 모듈의 참조 횟수를 1만큼 늘립니다.  
  
 DLL에 진입점 함수가 있으면 운영 체제에서는 `LoadLibrary`를 호출한 스레드 컨텍스트에서 이 함수를 호출합니다.  그러나 이전에 `LoadLibrary`를 호출하고 이에 대응하는 `FreeLibrary` 함수를 호출하지 않아서 DLL이 이미 프로세스에 연결되어 있으면 진입점 함수는 호출되지 않습니다.  
  
 확장 DLL을 로드하는 MFC 응용 프로그램의 경우 `LoadLibrary` 대신 `AfxLoadLibrary`를 사용하는 것이 좋습니다.  `AfxLoadLibrary`는 `LoadLibrary`를 호출하기 전에 스레드 동기화를 처리합니다.  `AfxLoadLibrary`에 대한 인터페이스\(함수 프로토타입\)는 `LoadLibrary`의 경우와 같습니다.  
  
 Windows에서 DLL을 로드할 수 없는 경우 프로세스는 오류 복구를 시도합니다.  예를 들어, 프로세스는 사용자에게 오류를 알려 사용자가 다른 DLL 경로를 지정하도록 할 수 있습니다.  
  
> [!IMPORTANT]
>  Windows NT 4, Windows 2000 또는 Windows XP\(SP1 이전 버전\)에서 코드를 실행할 때는 DLL의 전체 경로를 지정하십시오.  이러한 운영 체제에서는 파일을 로드할 때 현재 디렉터리를 먼저 검색합니다.  파일의 경로를 지정하지 않으면 의도하지 않은 파일이 로드될 수 있습니다.  
  
## 수행할 작업  
  
-   [암시적 링크](../build/linking-implicitly.md)  
  
-   [사용할 링크 방법 결정](../build/determining-which-linking-method-to-use.md)  
  
## 추가 정보  
  
-   [Windows에서 DLL을 찾는 데 사용되는 검색 경로](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   [FreeLibrary 및 AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)   
 [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187)   
 [AfxLoadLibrary](../Topic/AfxLoadLibrary.md)