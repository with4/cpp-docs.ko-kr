---
title: "_get_unexpected | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_unexpected"
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
  - "__get_unexpected"
  - "_get_unexpected"
  - "get_unexpected"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__get_unexpected 함수"
  - "_get_unexpected 함수"
  - "get_unexpected 함수"
ms.assetid: a5f7a7a0-18e0-485e-953d-db291068a1e8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _get_unexpected
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

종료 루틴이 `unexpected` 으로 호출되어 반환합니다.  
  
## 구문  
  
```  
unexpected_function _get_unexpected( void );  
```  
  
## 반환 값  
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md) 로 등록된 함수에 대한 포인터를 반환합니다.  만일 함수가 설정되어지지 않았다면, 반환값은 기본 동작을 저장하기 위해 사용될 것입니다; 이 값은 NULL일 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_get_unexpected`|\<eh.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)