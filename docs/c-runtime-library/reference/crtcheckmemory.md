---
title: "_CrtCheckMemory | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtCheckMemory"
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
  - "CrtCheckMemory"
  - "_CrtCheckMemory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtCheckMemory 함수"
  - "CrtCheckMemory 함수"
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtCheckMemory
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\(디버그 버전에만 해당\) 디버그 힙에 할당된 메모리 블록의 무결성을 확인합니다.  
  
## 구문  
  
```  
  
int _CrtCheckMemory( void );  
```  
  
## 반환 값  
 성공 하면  `_CrtCheckMemory`  는 TRUE를 반환합니다. 그렇지 않은 경우 FALSE를 반환합니다.  
  
## 설명  
 `_CrtCheckMemory`  함수를 원본으로 사용하는 기본 힙을 확인하고 모든 메모리 블록을 검사하여 디버그 힙 관리자에 의해 할당 된 메모리의 유효성을 검사합니다.  원본으로 사용하는 기본 힙, 디버그 헤더 정보 또는 덮어쓰기 버퍼에서 오류 또는 메모리 불일치가 발견되면  `_CrtCheckMemory` 는 오류 조건을 설명하는 정보를 사용하여 디버그 보고서를 생성합니다.  [\_DEBUG](../../c-runtime-library/debug.md)가 정의되어 있지 않으면 `_CrtCheckMemory` 에 대한 호출은 전처리 동안 제거됩니다.  
  
 `_CrtCheckMemory` 의 동작은 [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) 함수를 사용하는 [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그의 비트 필드를 설정하여 제어할 수 있습니다.  **\_CRTDBG\_CHECK\_ALWAYS\_DF**비트 필드를 활성화하면  `_CrtCheckMemory` 는 메모리 할당 작업이 요청될 때마다 호출됩니다.  이 메서드 실행 속도가 느리지만 빠르게 오류를 잡는 데 유용합니다.  **\_CRTDBG\_ALLOC\_MEM\_DF** 비트 필드를 해제하면  `_CrtCheckMemory` 는 힙을 확인하 고 즉시  **TRUE**를 반환합니다.  
  
 이 함수에서 **TRUE** 또는  **FALSE**를 반환 하기 때문에,  [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)매크로 중 하나에 전달 되어 간단한 디버깅 오류 처리 메커니즘을 만들 수 있습니다.  다음 예제에서는 힙 손상이 발견되면 어설션 오류가 발생하는 것을 확인할 수 있습니다:  
  
```  
_ASSERTE( _CrtCheckMemory( ) );  
```  
  
 어떻게  `_CrtCheckMemory`  가 다른 디버그 기능과 사용되는지에 대한 자세한 내용은   [힙 상태 보고 함수](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions)에서 참조하십시오.  메모리 관리 및 디버그 힙 사용 개요에 대한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md)을 참조 하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_CrtCheckMemory`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 예제  
 `_CrtCheckMemory` 을 사용하는 방법에 대한 예제는  [crt\_dbg1](http://msdn.microsoft.com/ko-kr/17b4b20c-e849-48f5-8eb5-dca6509cbaf9)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Diagnostics::PerformanceCounter](https://msdn.microsoft.com/en-us/library/system.diagnostics.performancecounter.aspx)  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)   
 [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)