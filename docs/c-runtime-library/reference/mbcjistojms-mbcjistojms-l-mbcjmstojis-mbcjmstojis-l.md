---
title: "_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l | Microsoft Docs"
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
  - "_mbcjistojms"
  - "_mbcjmstojis"
  - "_mbcjistojms_l"
  - "_mbcjmstojis_l"
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
  - "mbcjistojms"
  - "_mbcjistojms"
  - "_mbcjistojms_l"
  - "_mbcjmstojis_l"
  - "_mbcjmstojis"
  - "mbcjmstojis_l"
  - "mbcjistojms_l"
  - "mbcjmstojis"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbcjistojms 함수"
  - "_mbcjistojms_l 함수"
  - "_mbcjmstojis 함수"
  - "_mbcjmstojis_l 함수"
  - "mbcjistojms 함수"
  - "mbcjistojms_l 함수"
  - "mbcjmstojis 함수"
  - "mbcjmstojis_l 함수"
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일본 산업 표준 \(JIS\) 및 Microsoft 일본 \(JMS\) 문자 간에 변환합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
unsigned int _mbcjistojms(  
   unsigned int c   
);  
unsigned int _mbcjistojms_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbcjmstojis(  
   unsigned int c   
);  
unsigned int _mbcjmstojis_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 변환할 문자입니다.  
  
 `local`  
 사용할 로캘입니다.  
  
## 반환 값  
 일본어 로케일을 이러한 함수 변환된 문자를 반환하거나 변환이 불가능한 경우 0을 반환합니다.  일본어 이외의 언어로, 이러한 함수에 전달된 문자를 반환 합니다.  
  
## 설명  
 이 `_mbcjistojms` 함수는 일본 산업 표준 \(JIS\) 문자를 Microsoft 간지 \(Shift JIS\) 문자로 변환합니다.  문자 \-0x21 – 0x7E 범위에서 선행 및 후행 바이트 경우에 변환됩니다.  선행 혹은 후행 바이트가 이 범위를 벗어나는 경우, `errno` 은 `EILSEQ`을 설정합니다.  이 변경 내용 및 다른 오류 내용에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 이 `_mbcjmstojis`함수는 JIS 문자 Shift JIS 문자 변환 합니다.  문자는 0x81 – 0x9F 또는 0xE0 – 0xFC범위에서 선행 바이트는 후행 바이트 0x40\-0x7E 또는 0x80 – 0xFC 범위에는 경우에 변환됩니다.  범위에 할당된 문자없고 변환할 수 없는 일부 코드 포인트는 알립니다.  
  
 이 `c` 값은 상위 8 비트를 변환하려면 문자의 선행 바이트를 나타내고 하위 8 비트를 후행 바이트 16비트 값이어야 합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이전 버전에서는, `_mbcjistojms` 과 `_mbcjmstojis` 가 각각`jistojms` 이고 `jmstojis` 를 호출합니다.  `_mbcjistojms`,`_mbcjistojms_l`,`_mbcjmstojis` 및 `_mbcjmstojis_l` 를 대신 사용해야 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbcjistojms`|\<mbstring.h\>|  
|`_mbcjistojms_l`|\<mbstring.h\>|  
|`_mbcjmstojis`|\<mbstring.h\>|  
|`_mbcjmstojis_l`|\<mbstring.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [\_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)