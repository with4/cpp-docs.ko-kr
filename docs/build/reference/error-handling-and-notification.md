---
title: "오류 처리 및 알림 | Microsoft Docs"
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
  - "오류 처리, 알림"
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 오류 처리 및 알림
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오류 처리 및 알림에 대한 자세한 내용은 [도우미 함수 이해](http://msdn.microsoft.com/ko-kr/6279c12c-d908-4967-b0b3-cabfc3e91d3d)를 참조하십시오.  
  
 후크 함수에 대한 자세한 내용은 [구조체 및 상수 정의](../../build/reference/structure-and-constant-definitions.md)를 참조하십시오.  
  
 프로그램에서 지연 로드된 DLL을 사용하는 경우, 프로그램이 실행되는 동안 오류가 발생하면 처리되지 않은 예외가 발생하므로 강력한 방법으로 오류를 처리해야 합니다.  오류 처리는 다음 두 부분으로 이루어집니다.  
  
 후크를 통해 복구  
 오류가 발생했을 때 코드가 복구하거나 대체 라이브러리 및 루틴을 제공해야 하는 경우 그 상황을 제공하거나 복구할 수 있는 도우미 함수에 후크를 제공할 수 있습니다.  후크 루틴은 처리가 계속될 수 있도록 알맞은 값\(HINSTANCE 또는 FARPROC\)을 반환하거나 예외가 throw되어야 함을 알려주는 0을 반환해야 합니다.  또한 자체 예외를 throw하거나 후크 밖으로 **longjmp** 할 수도 있습니다.  후크에는 알림 후크와 오류 후크가 있습니다.  
  
 예외를 통해 알림  
 해당 프로시저를 중단하는 것만으로도 오류를 처리할 수 있는 경우 사용자 코드가 예외를 처리할 수 있으면 후크는 필요하지 않습니다.  
  
 다음 항목에서는 오류 처리 및 알림에 대해 설명합니다.  
  
-   [알림 후크](../../build/reference/notification-hooks.md)  
  
-   [오류 후크](../../build/reference/failure-hooks.md)  
  
-   [예외](../../build/reference/exceptions-c-cpp.md)  
  
## 참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)