---
title: "_CRTDBG_MAP_ALLOC | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRTDBG_MAP_ALLOC"
  - "_CRTDBG_MAP_ALLOC"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRTDBG_MAP_ALLOC 매크로"
  - "메모리 할당, 디버그 빌드"
  - "CRTDBG_MAP_ALLOC 매크로"
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CRTDBG_MAP_ALLOC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\_CRTDBG\_MAP\_ALLOC** 플래그가 응용 프로그램의 디버그 버전에서 정의된 경우 기본 힘 함수의 버전은 직접적으로 해당 디버그 버전에 매핑됩니다.  매핑을 수행하기 위해 Crtdbg.h에서 플래그를 사용합니다.  이 플래그는 [\_DEBUG](../c-runtime-library/debug.md) 플래그가 응용프로그램에서 정의되어졌을때만, 사용할 수 있습니다.  
  
 힘 함수의 기본 버전과 디버그 버전에 사용에 대한 비교는 [Using the Debug Version Versus the Base Version](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)를 참조하십시오.  
  
## 참고 항목  
 [제어 플래그](../c-runtime-library/control-flags.md)