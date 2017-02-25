---
title: "_ismbblead, _ismbblead_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbblead_l"
  - "_ismbblead"
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
  - "ismbblead_l"
  - "istlead"
  - "_ismbblead"
  - "_ismbblead_l"
  - "ismbblead"
  - "_istlead"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbblead_l 함수"
  - "ismbblead 함수"
  - "_ismbblead 함수"
  - "istlead 함수"
  - "ismbblead_l 함수"
  - "_istlead 함수"
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _ismbblead, _ismbblead_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자를 테스트하여 멀티바이트 문자의 선행 바이트인지 여부를 확인합니다.  
  
## 구문  
  
```  
int _ismbblead(  
   unsigned int c   
);  
int _ismbblead_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 정수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `c` 정수가 멀티바이트 문자의 첫 번째 바이트이면 0이 아닌 값을 반환합니다.  
  
## 설명  
 멀티바이트 문자는 선행 바이트와 그 뒤에 오는 후행 바이트로 구성됩니다. 선행 바이트는 지정된 문자 집합에 대한 특정 범위에 있는 것으로 구분됩니다. 예를 들어 코드 페이지 932에서만 선행 바이트의 범위는 0x81 – 0x9F에서 0xE0 – 0xFC 사이입니다.  
  
 `_ismbblead`은 로캘 종속 동작에 대해 현재 로캘을 사용합니다.`_ismbblead_l`은 전달된 로캘을 대신 사용한다는 점을 제외하고 동일합니다. 자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_istlead`|항상 false를 반환합니다.|`_ismbblead`|항상 false를 반환합니다.|  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_ismbblead`|\<mbctype.h\> 또는 \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
|`_ismbblead_l`|\<mbctype.h\> 또는 \<mbstring.h\>|\<ctype.h\>,\* \<limits.h\>, \<stdlib.h\>|  
  
 \* 테스트 조건에 대한 매니페스트 상수에 해당합니다.  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.  
  
## 참고 항목  
 [바이트 분류](../../c-runtime-library/byte-classification.md)   
 [\_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)