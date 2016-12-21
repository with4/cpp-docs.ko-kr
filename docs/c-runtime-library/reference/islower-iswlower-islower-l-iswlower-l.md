---
title: "islower, iswlower, _islower_l, _iswlower_l | Microsoft Docs"
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
  - "iswlower"
  - "_islower_l"
  - "islower"
  - "_iswlower_l"
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
  - "_istlower"
  - "islower"
  - "_ismbclower_l"
  - "_liswlower_l"
  - "_istlower_l"
  - "_iswlower_l"
  - "_islower _l"
  - "_islower_l"
  - "iswlower"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_islower _l 함수"
  - "_islower_l 함수"
  - "_ismbclower_l 함수"
  - "_istlower 함수"
  - "_istlower_l 함수"
  - "_iswlower_l 함수"
  - "_liswlower_l 함수"
  - "islower 함수"
  - "istlower 함수"
  - "iswlower 함수"
ms.assetid: fcc3b70a-2b47-45fd-944d-e5c1942e6457
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# islower, iswlower, _islower_l, _iswlower_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정수가 소문자를 나타내는지 여부를 확인합니다.  
  
## 구문  
  
```  
int islower(  
   int c   
);  
int iswlower(  
   wint_t c   
);  
int islower_l(  
   int c,  
   _locale_t locale  
);  
int _iswlower_l(  
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
 만약 `c` 가 소문자의 특정한 표현이면 각각의 이러한 루틴은 0이 아닌 값을 반환합니다.  `islower` 은 `c` 가 소문자\(a – z\) 인 경우 0이 아닌 값을 반환합니다.  `iswlower` 는 `c` 이 소문자에 해당하는 와이드 문자이거나 `c` 가 `iswcntrl`, `iswdigit`, `iswpunct`, 혹은 `iswspace` 가 0이 아닌 것들의 위한 와이드 문자 구현이 정의된 집합의 하나인 경우 0이 아닌 값을 반환합니다.  만약 `c` 가 테스트 조건을 만족하지 않는 경우 각각의 이러한 루틴은 0을 반환합니다.  
  
 여기서 `_l` 접미사가 있는 이러한 함수의 버전은 로캘 종속 동작에 대해 현재 로캘 대신 전달된 로캘을 사용합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 이 `islower` 와 `_islower_l` 의 동작은 `c` 가 EOF가 아니거나 0부터 0xFF 내에 포함되지 않는 경우 정의되지 않습니다.  디버그 CRT 라이브러리가 사용되고 `c`가 이들 값 중 하나가 아니면 함수에 어설션이 발생합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_istlower`|`islower`|[\_ismbclower](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`iswlower`|  
|`_istlower_l`|`_islower _l`|[\_ismbclower\_l](../../c-runtime-library/reference/ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|`_liswlower_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`islower`|\<ctype.h\>|  
|`iswlower`|\<ctype.h\> 또는 \<wchar.h\>|  
|`_islower_l`|\<ctype.h\>|  
|`_swlower_l`|\<ctype.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Char::IsLower](https://msdn.microsoft.com/en-us/library/system.char.islower.aspx)  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)