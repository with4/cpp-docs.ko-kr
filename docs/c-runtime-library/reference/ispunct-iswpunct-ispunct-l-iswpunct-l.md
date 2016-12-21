---
title: "ispunct, iswpunct, _ispunct_l, _iswpunct_l | Microsoft Docs"
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
  - "ispunct"
  - "_iswpunct_l"
  - "iswpunct"
  - "_ispunct_l"
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
  - "iswpunct"
  - "_istpunct"
  - "ispunct"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ispunct_l 함수"
  - "_istpunct 함수"
  - "_iswpunct_l 함수"
  - "ispunct 함수"
  - "ispunct_l 함수"
  - "istpunct 함수"
  - "iswpunct 함수"
  - "iswpunct_l 함수"
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ispunct, iswpunct, _ispunct_l, _iswpunct_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정수가 구두점 문자를 나타내는지 여부를 확인합니다.  
  
## 구문  
  
```  
int ispunct(  
   int c   
);  
int iswpunct(  
   wint_t c   
);  
int _ispunct_l(  
   int c,  
   _locale_t locale  
);  
int _iswpunct_l(  
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
 만약 `c` 가 구두점 문자의 특정한 표현이면 각각의 이러한 루틴은 0이 아닌 값을 반환합니다.  `ispunct` 는 `isalnum` 이 0이 아닌 공백 문자 또는 문자를 인쇄 가능한 모든 문자를 0이 아닌 값을 반환합니다.  `iswpunct` 는 `iswalnum` 가 0이 아닌 공간 와이드 문자 또는 와이드 문자를 인쇄할 수 있는 와이드 문자 0 이외의 값을 반환합니다.  만약 `c` 가 테스트 조건을 만족하지 않는 경우 각각의 이러한 루틴은 0을 반환합니다.  
  
 이 `ispunct` 함수의 테스트 조건 결과는 로캘의 `LC_CTYPE` 범주 설정에 따라 다릅니다. 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘을 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이 `ispunct` 와 `_ispunct_l` 의 동작은 `c` 이 EOF가 아니거나0부터 0xFF 내에 포함되지 않는 경우 정의되지 않는 경우 정의되지 않습니다.  디버그 CRT 라이브러리가 사용되고 `c`가 이들 값 중 하나가 아니면 함수에 어설션이 발생합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|**\_** `istpunct`|`ispunct`|[\_ismbcpunct](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswpunct`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`ispunct`|\<ctype.h\>|  
|`iswpunct`|\<ctype.h\> 또는 \<wchar.h\>|  
|`_ispunct_l`|\<ctype.h\>|  
|`_iswpunct_l`|\<ctype.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)