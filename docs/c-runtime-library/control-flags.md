---
title: "제어 플래그 | Microsoft Docs"
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
  - "c.flags"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "디버그 힙, 제어 플래그"
  - "플래그, 컨트롤"
  - "힙 할당, 제어 플래그"
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 제어 플래그
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft C 런타임 라이브러리의 디버그 버전은 힙 할당과 보고 프로세스를 제어하기 위해 다음의 플래그를 사용합니다.  자세한 내용은 [CRT 디버깅 기술](../Topic/CRT%20Debugging%20Techniques.md)을 참조하십시오.  
  
|플래그|설명|  
|---------|--------|  
|[\_CRTDBG\_MAP\_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|기본 힙 함수를 디버그 버전 counterparts에 맵핑합니다|  
|[\_DEBUG](../c-runtime-library/debug.md)|런타임 함수의 디버깅 버전을 사용할 수 있습니다.|  
|[\_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|디버그 힙 관리자가 어떻게 할당을 추적하는지를 제어합니다.|  
  
 이러한 플래그는 \/D 커맨드 라인 옵션이나 `#define` 명령을 사용하여 정의될 수 있습니다.  플래그가 `#define`를 통해 정의될 때, 명령은 반드시 루틴 선언을 하는 헤더 파일 include 지시문보다 앞에 위치해야 합니다.  
  
## 참고 항목  
 [전역 변수 및 표준 형식](../c-runtime-library/global-variables-and-standard-types.md)