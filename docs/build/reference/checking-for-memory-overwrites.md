---
title: "메모리 덮어쓰기 확인 | Microsoft Docs"
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
  - "메모리, 덮어쓰기"
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 메모리 덮어쓰기 확인
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙 조작 함수 호출 시 액세스 위반이 발생되면 프로그램이 힙을 손상시켰을 가능성이 있습니다.  이러한 경우의 일반적인 증상은 다음과 같습니다.  
  
```  
Access Violation in _searchseg  
```  
  
 [\_heapchk](../../c-runtime-library/reference/heapchk.md) 함수는 디버그 빌드와 릴리스 빌드 모두에서\(Windows NT에만 해당\) 런타임 라이브러리 힙의 무결성을 확인하는 데 사용할 수 있습니다.  `_heapchk`는 `AfxCheckMemory` 함수를 사용하여 힙 덮어쓰기를 확인하는 것과 같은 방법으로 사용할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 이 함수가 실패하는 경우에는 힙이 손상된 시점을 확인해야 합니다.  
  
## 참고 항목  
 [릴리스 빌드 문제 해결](../../build/reference/fixing-release-build-problems.md)