---
title: "_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbctohira"
  - "_mbctohira_l"
  - "_mbctokata"
  - "_mbctokata_l"
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
  - "_mbctokata"
  - "mbctohira"
  - "_mbctohira"
  - "_mbctohira_l"
  - "mbctokata"
  - "mbctokata_l"
  - "mbctohira_l"
  - "_mbctokata_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbctohira 함수"
  - "_mbctohira_l 함수"
  - "_mbctokata 함수"
  - "_mbctokata_l 함수"
  - "mbctohira 함수"
  - "mbctohira_l 함수"
  - "mbctokata 함수"
  - "mbctokata_l 함수"
ms.assetid: f949afd7-44d4-4f08-ac8f-1fef2c915a1c
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

히라가나 문자와 가타카나 문자 간에 변환합니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [CRT 함수는 \/ZW 옵션을 지원하지 않음](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)을 참조하세요.  
  
## 구문  
  
```  
unsigned int _mbctohira(  
   unsigned int c   
);  
unsigned int _mbctohira_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbctokata(  
   unsigned int c   
);  
unsigned int _mbctokata_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 변환할 멀티바이트 문자입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 가능한 경우 이러한 각 함수는 변환된 문자 `c`를 반환합니다.  그렇지 않으면 변환되지 않은 `c` 문자를 반환합니다.  
  
## 설명  
 `_mbctohira` 및 `_mbctokata` 함수는 문자 `c`를 테스트하고 가능한 경우 다음 변환 중 하나를 적용합니다.  
  
|루틴|변환|  
|--------|--------|  
|`_mbctohira,_mbctohira_l`|멀티바이트 가타카나를 멀티바이트 히라가나로 변환|  
|`_mbctokata,_mbctokata_l`|멀티바이트 히라가나를 멀티바이트 가타카나로 변환|  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요.  `_l` 접미사가 없는 함수는 이 로캘 종속 동작에 대해 현재 로캘을 사용하고 `_l` 접미사가 있는 함수는 전달되는 로캘 매개 변수를 대신 사용한다는 점을 제외하고 이러한 함수의 버전은 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
 이전 버전에서 `_mbctohira`의 이름은 `jtohira`였고 `_mbctokata`의 이름은 `jtokata`였습니다.  새 코드에서는 새 이름을 사용하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbctohira`|\<mbstring.h\>|  
|`_mbctohira_l`|\<mbstring.h\>|  
|`_mbctokata`|\<mbstring.h\>|  
|`_mbctokata_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [\_mbcjistojms, \_mbcjistojms\_l, \_mbcjmstojis, \_mbcjmstojis\_l](../../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)   
 [\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)   
 [\_mbctombb, \_mbctombb\_l](../../c-runtime-library/reference/mbctombb-mbctombb-l.md)