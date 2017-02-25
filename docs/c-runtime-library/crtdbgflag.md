---
title: "_crtDbgFlag | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_crtDbgFlag"
  - "crtDbgFlag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_crtDbgFlag 상수"
  - "crtDbgFlag 상수"
  - "디버그 힙, 제어 플래그"
  - "디버그 힙, 메모리 추적"
  - "메모리 할당 추적 플래그 사용"
  - "메모리 할당, 플래그 추적"
  - "메모리, 디버그 힙에서 추적"
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _crtDbgFlag
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\_crtDbgFlag** 플래그는 힙의 디버그 버전에서 메모리 할당을 추적, 확인, 보고 및 덤프하는 방법을 제어하는 비트 필드 5개로 구성됩니다.  플래그의 비트 필드는 [\_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) 함수를 사용하여 설정합니다.  이 플래그와 해당 비트 필드는 Crtdbg.h에서 선언됩니다.  이 플래그는 [\_DEBUG](../c-runtime-library/debug.md) 플래그를 응용 프로그램에서 정의한 경우에만 사용할 수 있습니다.  
  
 다른 디버그 함수와 함께 이 플래그 사용에 대한 자세한 내용은 [힙 상태 보고 함수](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions)를 참조하세요.  
  
## 참고 항목  
 [제어 플래그](../c-runtime-library/control-flags.md)