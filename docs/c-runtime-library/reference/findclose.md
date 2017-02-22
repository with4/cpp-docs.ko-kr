---
title: "_findclose | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_findclose"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_findclose"
  - "findclose"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_findclose 함수"
  - "findclose 함수"
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _findclose
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 검색 핸들을 닫고 관련된 리소스를 해제합니다.  
  
## 구문  
  
```  
int _findclose(   
   intptr_t handle   
);  
```  
  
#### 매개 변수  
 `handle`  
 이전 호출에 의해 `_findfirst`로 반환된 처리기를 검색합니다.  
  
## 반환 값  
 성공하면, `_findclose`는 0을 반환합니다.  그렇지 않으면 이는 \-1을 반환하고, `errno`를 더 이상 일치하는 파일을 찾을 수 없다는 뜻의 `ENOENT`로 설정합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_findclose`|\<io.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [시스템 호출](../../c-runtime-library/system-calls.md)   
 [파일 이름 검색 함수](../../c-runtime-library/filename-search-functions.md)