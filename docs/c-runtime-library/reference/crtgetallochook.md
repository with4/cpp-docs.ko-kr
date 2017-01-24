---
title: "_CrtGetAllocHook | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtGetAllocHook"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "CrtGetAllocHook"
  - "_CrtGetAllocHook"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtGetAllocHook 함수"
  - "CrtGetAllocHook 함수"
ms.assetid: 036acf7c-547a-4b3f-a636-80451070d7ed
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtGetAllocHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C 런타임 디버그 메모리 할당 프로세스\(디버그 버전에만 해당\)에 연결에 대하여 현재 할당 클라이언트가 정의된 함수를 검색합니다.  
  
## 구문  
  
```  
_CRT_ALLOC_HOOK _CrtGetAllocHook( void );  
```  
  
## 반환 값  
 현재 정의된 할당 후크 함수를 반환합니다.  
  
## 설명  
 `_CrtGetAllocHook`는 C 런타임 디버그 라이브러리 메모리 할당 프로세스에 대하여 현재 클라이언트가 정의된 응용 프로그램 후크 함수를 검색합니다.  
  
 다른 후크를 사용할 수 있는 런타임 함수를 사용하는 방법과 자신의 클라이언트 정의 후크 함수를 작성하는 방법에 대한 자세한 내용은  [디버그 후크 함수 작성](../Topic/Debug%20Hook%20Function%20Writing.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_CrtGetAllocHook`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_CrtSetAllocHook](../../c-runtime-library/reference/crtsetallochook.md)