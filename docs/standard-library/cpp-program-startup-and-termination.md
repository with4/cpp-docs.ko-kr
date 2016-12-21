---
title: "C++ Program Startup 및 Termination | Microsoft Docs"
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
  - "텍스트 스트림 제어"
  - "Function Main 프로시저"
  - "main 함수, 프로그램 시작"
  - "표준 C++ 라이브러리, 프로그램 시작 및 종료"
  - "시작 코드, C++ 프로그램 종료"
  - "실행 종료"
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C++ Program Startup 및 Termination
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A C\+\+ program performs the same operations as a C program does at program startup and at program termination, plus a few more outlined here.  
  
 Before the target environment calls the function `main`, and after it stores any constant initial values you specify in all objects that have static duration, the program executes any remaining constructors for such static objects.  The order of execution is not specified between translation units, but you can nevertheless assume that some [iostreams](../standard-library/iostreams-conventions.md) objects are properly initialized for use by these static constructors.  These control text streams are:  
  
-   [cin](../Topic/cin.md) — for standard input.  
  
-   [cout](../Topic/cout.md) — for standard output.  
  
-   [cerr](../Topic/cerr.md) — for unbuffered standard error output.  
  
-   [clog](../Topic/clog.md) — for buffered standard error output.  
  
 You can also use these objects within the destructors called for static objects, during program termination.  
  
 As with C, returning from `main` or calling `exit` calls all functions registered with `atexit` in reverse order of registry.  An exception thrown from such a registered function calls `terminate`.  
  
## 참고 항목  
 [STL 개요](../standard-library/cpp-standard-library-overview.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)