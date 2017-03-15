---
title: "C 및 Wind32를 사용한 다중 스레딩 | Microsoft Docs"
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
  - "다중 스레딩[C++], C 및 Win32"
  - "스레딩[C]"
  - "스레딩[C++], C 및 Win32"
  - "Visual C, 다중 스레딩"
  - "Win32[C++], 다중 스레딩"
  - "Win32 응용 프로그램[C++], 다중 스레딩"
  - "Windows API[C++], 다중 스레딩"
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# C 및 Wind32를 사용한 다중 스레딩
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Visual C\+\+는 Microsoft Windows\(Windows XP, Windows 2000, Windows NT, Windows Me 및 Windows 98\)를 사용한 다중 스레드 응용 프로그램 작성을 지원합니다.  응용 프로그램에서 키보드와 마우스의 동시 입력과 같은 다중 작업을 관리해야 하는 경우 스레드를 둘 이상 사용하는 것이 좋습니다.  한 스레드가 키보드 입력을 처리하는 동안 둘째 스레드는 마우스 동작을 필터링할 수 있습니다.  셋째 스레드는 마우스와 키보드 스레드의 데이터를 바탕으로 화면 표시를 업데이트할 수 있습니다.  이와 동시에 다른 스레드는 디스크 파일에 액세스하거나 통신 포트에서 데이터를 가져올 수 있습니다.  
  
 Visual C\+\+에서는 다중 스레드를 사용하여 프로그래밍할 수 있는 두 가지 방법, 즉 MFC\(Microsoft Foundation Class\) 라이브러리를 사용하거나 C 런타임 라이브러리와 Win32 API를 사용하는 방법이 있습니다.  MFC를 사용하여 다중 스레드 응용 프로그램을 만드는 방법을 보려면 C의 다중 스레딩 관련 항목을 읽은 후 [C\+\+ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)을 참조하십시오.  
  
 다음 항목에서는 다중 스레드 프로그램 만들기를 지원하는 Visual C\+\+ 기능을 설명합니다.  
  
## 추가 정보  
  
-   [다중 스레드 정보](../parallel/multithread-programs.md)  
  
-   [다중 스레딩을 위한 라이브러리 지원](../parallel/library-support-for-multithreading.md)  
  
-   [다중 스레딩을 위한 포함 파일](../parallel/include-files-for-multithreading.md)  
  
-   [스레드 컨트롤을 위한 C 런타임 라이브러리 함수](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [C의 다중 스레드 샘플 프로그램](../parallel/sample-multithread-c-program.md)  
  
-   [다중 스레드 Win32 프로그램 작성](../parallel/writing-a-multithreaded-win32-program.md)  
  
-   [다중 스레드 프로그램 컴파일 및 링크](../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [다중 스레드 프로그램으로 문제 영역 방지](../parallel/avoiding-problem-areas-with-multithread-programs.md)  
  
-   [TLS](../parallel/thread-local-storage-tls.md)  
  
## 참고 항목  
 [이전 코드를 위한 다중 스레드 지원\(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)