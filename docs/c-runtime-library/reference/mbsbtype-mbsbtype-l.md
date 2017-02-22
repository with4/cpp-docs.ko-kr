---
title: "_mbsbtype, _mbsbtype_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsbtype_l"
  - "_mbsbtype"
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
  - "mbsbtype"
  - "mbsbtype_l"
  - "_mbsbtype_l"
  - "_mbsbtype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsbtype 함수"
  - "_mbsbtype_l 함수"
  - "mbsbtype 함수"
  - "mbsbtype_l 함수"
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _mbsbtype, _mbsbtype_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

바이트 문자열의 형식을 반환합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _mbsbtype(  
   const unsigned char *mbstr,  
   size_t count   
);  
int _mbsbtype_l(  
   const unsigned char *mbstr,  
   size_t count,  
   _locale_t locale   
);  
```  
  
#### 매개 변수  
 `mbstr`  
 주소는 멀티 바이트 문자 시퀀스입니다.  
  
 `count`  
 바이트 오프셋에서 문자열의 머리입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `_mbsbtype` 및 `_mbsbtype_l`지정 된 바이트에서 테스트의 결과 나타내는 integer 값을 반환 합니다.  다음 표에 있는 매니페스트 상수는 Mbctype.h에 정의 되어 있습니다.  
  
|반환 값|형식: byte|  
|----------|--------------|  
|`_MBC_SINGLE` \(0\)|단일 문자  예를 들어, 코드 페이지 932에에서 `_mbsbtype` 0xDF 0x20\-0x7E 또는 0xA1 – 범위 내에서 지정 된 바이트는 0을 반환 합니다.|  
|`_MBC_LEAD` \(1\)|선행 바이트는 멀티 바이트 문자입니다.  예를 들어, 코드 페이지 932에에서 `_mbsbtype` 0xFC 0x81\-0x9F 또는 0xE0 – 범위 내에서 지정 된 바이트는 1을 반환 합니다.|  
|`_MBC_TRAIL` \(2\)|멀티 바이트 문자의 후행 바이트입니다.  예를 들어, 코드 페이지 932에에서 `_mbsbtype` 0xDF 0x20\-0x7E 또는 0xA1 – 범위 내에서 지정 된 바이트는 0을 반환 합니다.|  
|`_MBC_ILLEGAL` \(–1\)|`NULL` 문자열, 잘못 된 문자, 또는 `NULL` 바이트 `count` `mbstr`에서 바이트 오프셋에서 이전에 찾아졌습니다.|  
  
## 설명  
 `_mbsbtype` 함수는 멀티 바이트 문자열의 바이트의 형식을 결정 합니다.  함수는 바이트 오프셋 `count` 을 `mbstr` 에서만 검사합니다 , 지정한 바이트 앞에 잘못 된 문자를 무시 합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 `NULL`가 NULL인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `_MBC_ILLEGAL` 을 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_mbsbtype`|\<mbstring.h\>|\<mbctype.h\>|  
|`_mbsbtype_l`|\<mbstring.h\>|\<mbctype.h\>|  
  
 \* 매니페스트 상수에 대 한 반환 값을 사용합니다.  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 적용할 수 없는 경우, [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하십시오.  
  
## 참고 항목  
 [바이트 분류](../../c-runtime-library/byte-classification.md)