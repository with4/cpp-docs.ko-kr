---
title: "isupper, _isupper_l, iswupper, _iswupper_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "isupper"
  - "iswupper"
  - "_iswupper_l"
  - "_isupper_l"
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
  - "isupper"
  - "_istupper"
  - "iswupper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_istupper 함수"
  - "_isupper_l 함수"
  - "_iswupper_l 함수"
  - "istupper 함수"
  - "isupper 함수"
  - "isupper_l 함수"
  - "iswupper 함수"
  - "iswupper_l 함수"
ms.assetid: da2bcc9f-241c-48c0-9a0e-ad273827e16a
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# isupper, _isupper_l, iswupper, _iswupper_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정수가 대 문자를 나타내는지 여부를 확인합니다.  
  
## 구문  
  
```  
int isupper(  
   int c   
);  
int _isupper_l (  
   int c,  
   _locale_t locale  
);  
int iswupper(  
   wint_t c   
);  
int _iwsupper_l(  
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
 각 이러한 루틴은 `c` 이 특정한 대문자의 표현인 경우 0이 아닌 것을 반환합니다.  `isupper` 은 `c` 가 대문자\(A – Z\) 인 경우 0이 아닌 값을 반환합니다.  `iswupper` 는 `c` 이 대문자에 해당하는 와이드 문자이거나 `c` 가 `iswcntrl`, `iswdigit`, `iswpunct`, 혹은 `iswspace` 가 0이 아닌 것들의 위한 와이드 문자 구현이 정의된 집합의 하나인 경우 0이 아닌 값을 반환합니다.  만약 `c` 가 테스트 조건을 만족하지 않는 경우 각각의 이러한 루틴은 0을 반환합니다.  
  
 여기서 `_l` 접미사가 있는 이러한 함수의 버전은 로캘 종속 동작에 대해 현재 로캘 대신 전달된 로캘을 사용합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이 `isupper` 와 `_isupper_l` 의 동작은 `c` 가 EOF가 아니거나 0부터 0xFF 내에 포함되지 않는 경우 정의되지 않습니다.  디버그 CRT 라이브러리가 사용되고 `c`가 이들 값 중 하나가 아니면 함수에 어설션이 발생합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_istupper`|`isupper`|[\_ismbcupper](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`iswupper`|  
|`_istupper_l`|`_isupper_l`|[\_ismbclower, \_ismbclower\_l, \_ismbcupper, \_ismbcupper\_l](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`_iswupper_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`isupper`|\<ctype.h\>|  
|`_isupper_l`|\<ctype.h\>|  
|`iswupper`|\<ctype.h\> 또는 \<wchar.h\>|  
|`_iswupper_l`|\<ctype.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Char::IsUpper](https://msdn.microsoft.com/en-us/library/system.char.isupper.aspx)  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)