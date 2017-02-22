---
title: "_CrtGetReportHook | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtGetReportHook"
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
  - "CrtGetReportHook"
  - "_CrtGetReportHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CrtGetReportHook 함수"
  - "_CrtGetReportHook 함수"
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtGetReportHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

디버그 보고 프로세스 \(디버그 버전에만 해당\) 대해서 런타임 C에 연결하기 위한 클라이언트 정의 보고 함수를 검색합니다.  
  
## 구문  
  
```  
_CRT_REPORT_HOOK _CrtGetReportHook( void );  
```  
  
## 반환 값  
 현재의 클라이언트 정의 보고 함수를 반환합니다.  
  
## 설명  
 `_CrtGetReportHook`는 프로그램이 C 런타임 디버그 라이브러리 보고 프로세스의 현재 보고 함수를 검색할 수 있도록 해줍니다.  
  
 다른 후크를 사용할 수 있는 런타임 함수를 사용하는 방법과 자신의 클라이언트 정의 후크 함수를 작성하는 방법에 대한 자세한 내용은  [디버그 후크 함수 작성](../Topic/Debug%20Hook%20Function%20Writing.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_CrtGetReportHook`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 예제  
 `_CrtSetReportHook`를 사용하는 방법에 대한 예제는 [report](http://msdn.microsoft.com/ko-kr/f6e08c30-6bd9-459a-830a-56deec0d2051)를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md)