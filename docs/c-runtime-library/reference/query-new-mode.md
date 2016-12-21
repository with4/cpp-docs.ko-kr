---
title: "_query_new_mode | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_query_new_mode"
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
  - "query_new_mode"
  - "_query_new_mode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_query_new_mode 함수"
  - "처리기 모드"
  - "query_new_mode 함수"
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _query_new_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`malloc` 에 대해 `_set_new_mode` 에 의해 설정된 새 처리기모드를 나타내는 정수를 반환합니다.  
  
## 구문  
  
```  
  
      int _query_new_mode(  
   void   
);  
```  
  
## 반환 값  
 `malloc`에 대한, 현재 새 처리기 모드, 즉 0 또는 1을 반환합니다.  1의 반환 값은 메모리 할당의 실패를 나타내며, `malloc`은 새 처리기 루틴을 호출합니다. 0의 반환 값은 그렇지 않다는 것을 의미합니다.  
  
## 설명  
 C\+\+ `_query_new_mode` 함수는 [malloc](../../c-runtime-library/reference/malloc.md) 에 대한 C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) 함수에 의해 설정된 새 처리기 모드를 가리키는 정수를 반환합니다.  새 처리기 모드는 메모리 할당에 대해 실패 시 `malloc`이 [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지 여부를 나타냅니다.  기본적으로 `malloc`은 실패한 경우 새 처리기 루틴을 호출하지 않습니다.  메모리를 할당하는 것에 실패했을 때, **new** 연산자가 실행하는 것과 같은 방식으로 `malloc` 은 새 처리기 루틴을 호출하는 이 동작이 실패할 경우에 이 동작을 오버라이드하기 위해 `_set_new_mode` 를 사용할 수 있습니다.  보다 자세한 정보는, *C\+\+ 언어 참조* 에서 [new 연산자](../../misc/operator-new-function.md) 함수와 [delete 연산자](../../misc/operator-delete-function.md)를 참고하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_query_new_mode`|\<new.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_query\_new\_handler](../../c-runtime-library/reference/query-new-handler.md)