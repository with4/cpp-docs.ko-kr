---
title: "isalnum, iswalnum, _isalnum_l, _iswalnum_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_iswalnum_l"
  - "_isalnum_l"
  - "iswalnum"
  - "isalnum"
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
  - "_istalnum_l"
  - "_iswalnum_l"
  - "iswalnum"
  - "_isalnum_l"
  - "isalnum"
  - "_istalnum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_isalnum_l 함수"
  - "_ismbcalnum_l 함수"
  - "_istalnum 함수"
  - "_istalnum_l 함수"
  - "_iswalnum_l 함수"
  - "isalnum 함수"
  - "istalnum 함수"
  - "iswalnum 함수"
ms.assetid: 0dc51306-ade8-4944-af27-e4176fc89093
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# isalnum, iswalnum, _isalnum_l, _iswalnum_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

영숫자 문자가 정수를 나타내는지 여부를 확인 합니다.  
  
## 구문  
  
```  
int isalnum(   
   int c   
);  
int iswalnum(   
   wint_t c   
);  
int _isalnum_l(   
   int c,  
   _locale_t locale  
);  
int _iswalnum_l(   
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
 이러한 각 루틴 반환이 0이 아닌 경우 `c` 는 영숫자 문자를 특정 표시 합니다.  `isalnum` 는 0이 아닌 값을 반환 합니다. 만약 `isalpha` 또는 `isdigit` 에 대해 0이 아닐 경우, `c`, 즉, `c` A – Z 범위 내 a – z 또는 0\-9일 경우입니다.  `iswalnum` 경우 0이 아닌 값을 반환 합니다. `iswalpha` 또는 `iswdigit` 에 대해 0이 아닌 `c`.  만약 `c` 가 테스트 조건을 만족하지 않는 경우 각각의 이러한 루틴은 0을 반환합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이 `isalnum` 와 `_isalnum_l` 의 동작은 `c` 가 EOF가 아니거나 0부터 0xFF 내에 포함되지 않는 경우 정의되지 않습니다.  디버그 CRT 라이브러리가 사용되고 `c`가 이들 값 중 하나가 아니면 함수에 어설션이 발생합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_istalnum`|`isalnum`|[\_ismbcalnum](../../c-runtime-library/reference/ismbcalnum-functions.md)|`iswalnum`|  
|`_istalnum_l`|`_isalnum_l`|`_ismbcalnum_l`|`_iswalnum_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`isalnum`|\<ctype.h\>|  
|`iswalnum`|\<ctype.h\> 또는 \<wchar.h\>|  
|`_isalnum_l`|\<ctype.h\>|  
|`_iswalnum_l`|\<ctype.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Char::IsLetterOrDigit](https://msdn.microsoft.com/en-us/library/system.char.isletterordigit.aspx).  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)