---
title: "_mbctombb, _mbctombb_l | Microsoft Docs"
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
  - "_mbctombb_l"
  - "_mbctombb"
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
  - "_mbctombb_l"
  - "_mbctombb"
  - "mbctombb_l"
  - "mbctombb"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbctombb 함수"
  - "_mbctombb_l 함수"
  - "mbctombb 함수"
  - "mbctombb_l 함수"
ms.assetid: d90970b8-71ff-4586-b6a2-f9ceb811f776
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbctombb, _mbctombb_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

해당 단일 바이트 멀티 바이트 문자를 더블 바이트 멀티 바이트 문자를 변환합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
unsigned int _mbctombb(  
   unsigned int c   
);  
unsigned int _mbctombb_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 멀티 바이트 문자를 변환 합니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 성공하는 경우, `_mbctombb` 과 `_mbctombb_l`는, 그렇지 않으면 `c` 를 반환하는, `c`으로 일치하는 단일 바이트 문자를 반환합니다.  
  
## 설명  
 이 `_mbctombb` 과 `_mbctombb_l`함수는 단일 바이트 멀티 바이트 문자를 해당 특정된 멀티 바이트 문자 변환합니다.  문자 변환 0xDF 0x20\-0x7E 또는 0xA1\-범위 내의 단일 바이트 문자를 일치해야 합니다.  
  
 출력값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 을 참조하십시오.  이 `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이전 버전에서는, `_mbctombb` 는 `zentohan`를 호출합니다.  대신 \_`mbctombb` 를 사용하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbctombb`|\<mbstring.h\>|  
|`_mbctombb_l`|\<mbstring.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [\_mbbtombc, \_mbbtombc\_l](../../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)   
 [\_mbcjistojms, \_mbcjistojms\_l, \_mbcjmstojis, \_mbcjmstojis\_l](../../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)   
 [\_mbctohira, \_mbctohira\_l, \_mbctokata, \_mbctokata\_l](../../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)   
 [\_mbctolower, \_mbctolower\_l, \_mbctoupper, \_mbctoupper\_l](../../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)