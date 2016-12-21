---
title: "isspace, iswspace, _isspace_l, _iswspace_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "iswspace"
  - "_isspace_l"
  - "_iswspace_l"
  - "isspace"
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
  - "iswspace"
  - "_istspace"
  - "isspace"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_isspace_l 함수"
  - "_istspace 함수"
  - "_iswspace_l 함수"
  - "isspace 함수"
  - "isspace_l 함수"
  - "istspace 함수"
  - "iswspace 함수"
  - "iswspace_l 함수"
ms.assetid: b851e0c0-36bb-4dac-a1a3-533540939035
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isspace, iswspace, _isspace_l, _iswspace_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정수가 공백 문자를 나타내는지 여부를 확인합니다.  
  
## 구문  
  
```  
int isspace(  
   int c   
);  
int iswspace(  
   wint_t c   
);  
int _isspace_l(  
   int c,  
   _locale_t locale  
);  
int _iswspace_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 정수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 만약 `c` 가 공백 문자의 특정한 표현이면 각각의 이러한 루틴은 0이 아닌 값을 반환합니다.  `isspace` 는 `c` 가 공백 문자\(0x09 – 0x0D 또는 0x20\) 인 경우 0이 아닌 값을 반환합니다.   `isspace` 함수의 테스트 조건 결과는 로캘의 `LC_CTYPE` 범주 설정에 따라 다릅니다. 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘을 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 `iswspace` 은 `c` 가 표준 공백 문자에 해당하는 와이드 문자인 경우 0이 아닌 값을 반환 합니다.  
  
 `isspace` 와 `_isspace_l` 의 동작은 `c` 가 EOF가 아니거나 0부터 0xFF 내에 포함되지 않는 경우 정의되지 않습니다.  디버그 CRT 라이브러리가 사용되고 `c`가 이들 값 중 하나가 아니면 함수에 어설션이 발생합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|**\_** `istspace`|`isspace`|[\_ismbcspace](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswspace`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`isspace`|\<ctype.h\>|  
|`iswspace`|\<ctype.h\> 또는 \<wchar.h\>|  
|`_isspace_l`|\<ctype.h\>|  
|`_iswspace_l`|\<ctype.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Char::IsWhiteSpace](https://msdn.microsoft.com/en-us/library/system.char.iswhitespace.aspx)  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)