---
title: "toascii, __toascii | Microsoft Docs"
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
  - "__toascii"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__toascii"
  - "toascii"
  - "ctype/toascii"
  - "ctype/__toascii"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "toascii 함수"
  - "ASCII 문자를 문자열 변환"
  - "__toascii 함수"
  - "ASCII 문자를 변환"
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# toascii, __toascii
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

잘라내기를 통한를 7 비트 ASCII 문자를 변환합니다.  
  
## 구문  
  
```  
int __toascii(  
   int c   
);  
#define toascii __toascii  
```  
  
#### 매개 변수  
 `c`  
 변환할 문자입니다.  
  
## 반환 값  
 `__toascii` 값으로 변환 `c` 7 비트 ascii 범위 및 결과 반환 합니다. 오류를 나타내는 데 예약 된 반환 값이 없는 있습니다.  
  
## 설명  
 `__toascii` 루틴 하위 7 비트를 잘라 지정 된 문자는 ASCII 문자를 변환 합니다. 다른 변환이 적용 됩니다.  
  
 `__toascii` 전처리기 매크로 \_CTYPE\_DISABLE\_MACROS 정의 되어 있지 않으면 루틴 매크로로 정의 됩니다. 이전 버전과 호환성을 위해 `toascii` 매크로로 정의 된 경우에만 [\_\_STDC\_\_](../../preprocessor/predefined-macros.md) 정의 되지 않았거나 0;으로 정의 그렇지 않으면 정의 되지 않습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`toascii`, `__toascii`|C: \< ctype.h \><br /><br /> C \+ \+: \< cctype \> 또는 \< ctype.h \>|  
  
 `toascii` 매크로는 POSIX 확장 및 `__toascii` POSIX 확장의 Microsoft 관련 구현입니다. 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)   
 [to 함수](../../c-runtime-library/to-functions.md)