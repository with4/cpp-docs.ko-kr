---
title: "btowc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "btowc"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "btowc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "btowc 함수"
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# btowc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

초기 시프트 상태에서 유효한 단일 바이트 문자는 정수를 나타내는지 여부를 확인합니다.  
  
## 구문  
  
```  
wint_t btowc(  
   int c  
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 정수입니다.  
  
## 반환 값  
 초기 시프트 상태에서 만일 정수가 유효한 단일 바이트 문자를 나타낸다면, 문자의 와이드 문자 표현을 반환합니다.  초기 시프트 상태에서 정수가 EOF이거나 유효한 단일 바이트 문자가 아니라면 WEOF를 반환합니다.  이 함수의 출력은 현재 `LC_TYPE` 로캘로 영향을 받습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`btowc`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)