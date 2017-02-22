---
title: "isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_iswxdigit_l"
  - "iswxdigit"
  - "isxdigit"
  - "_isxdigit_l"
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
  - "iswxdigit"
  - "isxdigit"
  - "_istxdigit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_istxdigit 함수"
  - "_iswxdigit_l 함수"
  - "_isxdigit_l 함수"
  - "16진수 문자"
  - "istxdigit 함수"
  - "iswxdigit 함수"
  - "iswxdigit_l 함수"
  - "isxdigit 함수"
  - "isxdigit_l 함수"
ms.assetid: c8bc5146-0b58-4e3f-bee3-f2318dd0f829
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# isxdigit, iswxdigit, _isxdigit_l, _iswxdigit_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정수를 16 진수 문자를 나타내는지 여부를 확인합니다.  
  
## 구문  
  
```  
int isxdigit(  
   int c   
);  
int iswxdigit(  
   wint_t c   
);  
int _isxdigit_l(  
   int c,  
   _locale_t locale  
);  
int _iswxdigit_l(  
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
 만약 `c` 가 16진수 문자의 특정한 표현이면 각각의 이러한 루틴은 0이 아닌 값을 반환합니다.  `isxdigit` 은 `c` 이 16진수 숫자\(A – F, a – f, or 0 – 9\)인 경우 0이 아닌 값을 반환합니다.  만약 `c` 가 16진수 숫자에 해당하는 와이드 문자라면 `iswxdigit` 는 0이 아닌 값을 반환합니다.  만약 `c` 가 테스트 조건을 만족하지 않는 경우 각각의 이러한 루틴은 0을 반환합니다.  
  
 "C" 로케일의 `iswxdigit` 함수는 전자의 16 진수 문자 유니코드를 지원 하지 않습니다.  
  
 여기서 `_l` 접미사가 있는 이러한 함수의 버전은 로캘 종속 동작에 대해 현재 로캘 대신 전달된 로캘을 사용합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이 `isxdigit` 와 `_isxdigit_l` 의 동작은 `c` 가 EOF가 아니거나 0부터 0xFF 내에 포함되지 않는 경우 정의되지 않습니다.  디버그 CRT 라이브러리가 사용되고 `c`가 이들 값 중 하나가 아니면 함수에 어설션이 발생합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_istxdigit`|`isxdigit`|`isxdigit`|`iswxdigit`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`isxdigit`|\<ctype.h\>|  
|`iswxdigit`|\<ctype.h\> 또는 \<wchar.h\>|  
|`_isxdigit_l`|\<ctype.h\>|  
|`_iswxdigit_l`|\<ctype.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Char::IsNumber](https://msdn.microsoft.com/en-us/library/system.char.isnumber.aspx)  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)