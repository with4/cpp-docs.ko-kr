---
title: "_set_new_mode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_new_mode"
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
  - "set_new_mode"
  - "_set_new_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_new_mode 함수"
  - "처리기 모드"
  - "set_new_mode 함수"
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _set_new_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`malloc`의 새 처리기 모드를 설정합니다.  
  
## 구문  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### 매개 변수  
 `newhandlermode`  
 `malloc`의 새 처리기 모드입니다. 유효한 값은 0 또는 1입니다.  
  
## 반환 값  
 `malloc`의 이전 처리기 모드를 반환합니다.  1의 반환 값은 메모리 할당의 실패를 나타내며, `malloc`은 이전에 새 처리기 루틴을 호출합니다. 0의 반환 값은 그렇지 않다는 것을 의미합니다.  `newhandlermode` 인수가 0 또는 1과 같지 않다면, \-1을 반환합니다.  
  
## 설명  
 C\+\+의 `_set_new_mode` 함수는 [malloc](../../c-runtime-library/reference/malloc.md)의 새로운 처리기 모드를 설정합니다.  새 처리기 모드는 실패 시 `malloc`이 [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지 여부를 나타냅니다.  기본적으로 `malloc`은 메모리 할당에 실패한 경우 새 처리기 루틴을 호출하지 않습니다.  `malloc`이 메모리 할당에 실패하면 `malloc`이 새 처리기 루틴을 `new` 연산자가 같은 이유로 실패할 때와 동일한 방식으로 호출할 수 있도록 기본 동작을 재정의할 수 있습니다.  자세한 내용은, *C\+\+ Language Reference*에서 [new](../../cpp/new-operator-cpp.md) 및 [delete](../../cpp/delete-operator-cpp.md) 연산자를 참조하십시오.  기본값을 재정의하려면 다음을 호출합니다.  
  
```  
_set_new_mode(1)  
```  
  
 초기 프로그램 또는 Newmode.obj에 대한 링크\([링크 옵션](../../c-runtime-library/link-options.md) 참조\).  
  
 이 함수는 매개변수를 인증합니다.  `newhandlermode`이 0 또는 1 외의 다른 값인 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된대로 이 함수는 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, **\_**`set_new_mode` 은 \-1을 반환하고, `errno`에 `EINVAL`를 설정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_set_new_mode`|\<new.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_query\_new\_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [\_query\_new\_mode](../../c-runtime-library/reference/query-new-mode.md)