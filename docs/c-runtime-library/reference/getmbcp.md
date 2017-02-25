---
title: "_getmbcp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getmbcp"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getmbcp"
  - "getmbcp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_getmbcp 함수"
  - "코드 페이지, 현재 코드 페이지 확인"
  - "getmbcp 함수"
ms.assetid: 2db202d4-5c3d-4871-a0b8-ceb0b79ee7bb
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _getmbcp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 코드 페이지를 검색합니다.  
  
## 구문  
  
```  
int _getmbcp( void );  
```  
  
## 반환 값  
 현재 멀티 바이트 코드 페이지를 반환합니다.  반환 값 0은 단일 바이트 코드 페이지를 사용 중임을 나타냅니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_getmbcp`|\<mbctype.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)