---
title: "_aligned_free | Microsoft Docs"
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
  - "_aligned_free"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "aligned_free"
  - "_aligned_free"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_aligned_free 함수"
  - "aligned_free 함수"
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_free
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) 또는 [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)으로 할당된 메모리 블록을 해제합니다.  
  
## 구문  
  
```  
void _aligned_free (  
   void *memblock  
);  
```  
  
#### 매개 변수  
 `memblock`  
 반환 된 메모리 블록에 대 한 포인터는 `_aligned_malloc` 또는 `_aligned_offset_malloc` 함수입니다.  
  
## 설명  
 `_aligned_free` 는 `__declspec(noalias)` 로 표시됩니다, 함수는 전역 변수를 수정할 수는 없다는 것을 보장합니다.  더 자세한 내용은 [주석](../../cpp/noalias.md)을 참조하십시오.  
  
 이 함수는 다른 \_aligned CRT 함수와 달리 매개 변수를 유효성 검사하지 않습니다.  만일 `memblock` 이 `NULL` 포인터일 경우, 이 함수는 단순하게 아무 실행도 하지 않습니다.  이는 `errno` 를 변경하지 않고, 잘못된 매개 변수 처리기를 호출하지 않습니다.  만일 이전에 \_aligned 함수가 메모리 블럭에 할당하는 데 사용되지 못했기 때문에 오류가 함수에서 발생한다면, 또는 일부 예측하지 못한 재앙때문에 메모리의 misalignment 발생한다면, 함수는 디버그 리포트를 [\_RPT, \_RPTF, \_RPTW, \_RPTFW 매크로](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)로부터 발생시킵니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_aligned_free`|\<malloc.h\>|  
  
## 예제  
 더 자세한 내용은 [\_malloc\_dbg](../../c-runtime-library/reference/aligned-malloc.md)를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 맞춤](../../c-runtime-library/data-alignment.md)