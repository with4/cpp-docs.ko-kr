---
title: "_mbbtombc, _mbbtombc_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbbtombc_l"
  - "_mbbtombc"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbbtombc_l"
  - "_mbbtombc"
  - "mbbtombc_l"
  - "mbbtombc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbbtombc 함수"
  - "_mbbtombc_l 함수"
  - "mbbtombc 함수"
  - "mbbtombc_l 함수"
ms.assetid: 78593389-b0fc-43b6-8c1f-2a6bf702d64e
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _mbbtombc, _mbbtombc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

싱글바이트 멀티바이트 문자를 해당 더블바이트 멀티바이트 문자로 변환합니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
unsigned int _mbbtombc(  
   unsigned int c   
);  
unsigned int _mbbtombc_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 변환할 싱글바이트 문자입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `_mbbtombc`가 `c`를 성공적으로 변환한 경우 멀티바이트 문자를 반환합니다. 그렇지 않으면 `c`를 반환합니다.  
  
## 설명  
 `_mbbtombc` 함수는 지정된 싱글바이트 멀티바이트 문자를 해당 더블바이트 멀티바이트 문자로 변환합니다.  문자를 변환하려면 0x20 \- 0x7E 또는 0xA1 \- 0xDF 범위 내에 있어야 합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요.  이 버전의 함수는 `_mbbtombc`가 이 로캘 종속 동작의 현재 로캘을 사용하고 `_mbbtombc_l`은 전달된 로캘 매개 변수를 사용한다는 점을 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 이전 버전에서 `_mbbtombc`의 이름은 `hantozen`입니다.  새 코드의 경우 `_mbbtombc`를 사용합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbbtombc`|\<mbstring.h\>|  
|`_mbbtombc_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [\_mbctombb, \_mbctombb\_l](../../c-runtime-library/reference/mbctombb-mbctombb-l.md)