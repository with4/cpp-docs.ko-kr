---
title: "_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbctolower_l"
  - "_mbctoupper_l"
  - "_mbctoupper"
  - "_mbctolower"
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
  - "mbctoupper_l"
  - "mbctolower_l"
  - "_mbctolower"
  - "_mbctolower_l"
  - "_mbctoupper"
  - "mbctoupper"
  - "mbctolower"
  - "_mbctoupper_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbctolower 함수"
  - "_mbctolower_l 함수"
  - "_mbctoupper 함수"
  - "_mbctoupper_l 함수"
  - "_totlower 함수"
  - "_totupper 함수"
  - "mbctolower 함수"
  - "mbctolower_l 함수"
  - "mbctoupper 함수"
  - "mbctoupper_l 함수"
  - "totlower 함수"
  - "totupper 함수"
ms.assetid: 787fab71-3224-4ed7-bc93-4dcd8023fc54
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

테스트 및 멀티 바이트 문자 대\/소문자를 변환 합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
unsigned int _mbctolower(  
   unsigned int c   
);  
unsigned int _mbctolower_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbctoupper(  
   unsigned int c   
);  
unsigned int _mbctoupper_l(  
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
 가능하면, 이러한 각각의 함수는 변환된 문자 `c`를 반환합니다.  그렇지 않으면 부호가 없는 `c` 문자를 반환합니다.  
  
## 설명  
 문자를 테스트 하는 함수는 `c` 및 다음 변환 중 하나를 적용 가능한 경우.  
  
|루틴|AFX\_IDD\_CONVERT|  
|--------|-----------------------|  
|`_mbctolower,_mbctolower_l`|대문자에서 소문자|  
|`_mbctoupper,_mbctoupper_l`|대문자에서 소문자|  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이전 버전에서는 `_mbctolower` 호출된`jtolower`, 및 `_mbctoupper` 호출된 `jtoupper`.  새 코드는 새 이름을 대신 사용 하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_totlower`|`tolower`|`_mbctolower`|`towlower`|  
|`_totlower_l`|`_tolower_l`|`_mbctolower_l`|`_towlower_t`|  
|`_totupper`|`toupper`|`_mbctoupper`|`towupper`|  
|`_totupper_l`|`toupper_l`|`_mbctoupper_l`|`_towupper_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mbctolower,_mbctolower_l`|\<mbstring.h\>|  
|`_mbctoupper,_mbctoupper_l`|\<mbstring.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [\_mbbtombc, \_mbbtombc\_l](../../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)   
 [\_mbcjistojms, \_mbcjistojms\_l, \_mbcjmstojis, \_mbcjmstojis\_l](../../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)   
 [\_mbctohira, \_mbctohira\_l, \_mbctokata, \_mbctokata\_l](../../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)   
 [\_mbctombb, \_mbctombb\_l](../../c-runtime-library/reference/mbctombb-mbctombb-l.md)