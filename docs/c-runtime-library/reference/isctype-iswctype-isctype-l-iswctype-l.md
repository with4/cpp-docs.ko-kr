---
title: "_isctype, iswctype, _isctype_l, _iswctype_l | Microsoft Docs"
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
  - "_isctype_l"
  - "iswctype"
  - "_iswctype_l"
  - "_isctype"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "iswctype"
  - "_isctype"
  - "_isctype_l"
  - "_iswctype"
  - "isctype"
  - "iswctype_l"
  - "isctype_l"
  - "_iswctype_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_isctype 함수"
  - "_isctype_l 함수"
  - "_iswctype 함수"
  - "_iswctype_l 함수"
  - "isctype 함수"
  - "isctype_l 함수"
  - "iswctype 함수"
  - "iswctype_l 함수"
ms.assetid: cf7509b7-12fc-4d95-8140-ad2eb98173d3
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _isctype, iswctype, _isctype_l, _iswctype_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 `desc` 인수로 지정된 속성의 `c` 을 테스트합니다.  각 `desc` 유효한 값의, 와이드 분류 해당하는 루틴입니다.  
  
## 구문  
  
```  
int _isctype(  
   int c,  
   _ctype_t desc  
);  
int _isctype_l(  
   int c,  
   _ctype_t desc,  
   _locale_t locale  
);  
int iswctype(  
   wint_t c,  
   wctype_t desc   
);  
int _iswctype_l(  
   wint_t c,  
   wctype_t desc,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 정수입니다.  
  
 `desc`  
 테스트를 위한 속성입니다.  ctype 혹은 [wctype](../../c-runtime-library/reference/wctype.md)을 사용하는 일반적으로 검색됩니다.  
  
 `locale`  
 모든 로캘 종속 테스트에 사용할 로캘입니다.  
  
## 반환 값  
 `_isctype` 와 `iswctype` 은 `c` 가 현재 로캘의 `desc` 에 지정된 속성을 가진 경우나 0이 아닌 경우에 0이 아닌 값을 반환합니다.  `_l` 접미사가 있는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이 `_isctype` 와 `_isctype_l` 의 동작은 `c` 가 EOF가 아니거나 0부터 0xFF 내에 포함되지 않는 경우 정의되지 않습니다.  디버그 CRT 라이브러리가 사용되고 `c`가 이들 값 중 하나가 아니면 함수에 어설션이 발생합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`n/a`|`_isctype`|`n/a`|`_iswctype`|  
|`n/a`|`_isctype_l`|`n/a`|`_iswctype_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_isctype`|\<ctype.h\>|  
|`iswctype`|\<ctype.h\> 또는 \<wchar.h\>|  
|`_isctype_l`|\<ctype.h\>|  
|`_iswctype_l`|\<ctype.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)