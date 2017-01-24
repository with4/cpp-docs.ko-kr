---
title: "_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l | Microsoft Docs"
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
  - "_ismbclegal_l"
  - "_ismbclegal"
  - "_ismbcsymbol"
  - "_ismbcsymbol_l"
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
  - "ismbcsymbol_l"
  - "_ismbcsymbol_l"
  - "_ismbcsymbol"
  - "_ismbclegal_l"
  - "_ismbclegal"
  - "ismbclegal_l"
  - "ismbcsymbol"
  - "ismbclegal"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbclegal 함수"
  - "_ismbclegal_l 함수"
  - "_ismbcsymbol 함수"
  - "_ismbcsymbol_l 함수"
  - "_istlegal 함수"
  - "_istlegal_l 함수"
  - "ismbclegal 함수"
  - "ismbclegal_l 함수"
  - "ismbcsymbol 함수"
  - "ismbcsymbol_l 함수"
  - "istlegal 함수"
  - "istlegal_l 함수"
ms.assetid: 31bf1ea5-b56f-4e28-b21e-b49a2cf93ffc
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

법적 멀티 바이트 문자 인지 확인하거나 기호 문자입니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _ismbclegal(  
   unsigned int c   
);  
int _ismbclegal_l(  
   unsigned int c,   
   _locale_t locale  
);  
int _ismbcsymbol(  
   unsigned int c   
);  
int _ismbcsymbol_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 문자입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 이러한 각 루틴은 이 문자가 테스트 조건을 만족하는 경우 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다.  `c`\<\= 255 및 해당 하는 `_ismbb` 루틴인 경우 \(예를 들어, `_ismbcalnum` 에 반응하는 `_ismbbalnum`\), 결과는 `_ismbb` 루틴에 응답하는 반환값 입니다.  
  
## 설명  
 이러한 각 함수는 지정한 조건에 대해 주어진 멀티바이트 문자를 테스트합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
|루틴|테스트 조건|932 코드 페이지 예제|  
|--------|------------|-------------------|  
|`_ismbclegal`|유효한 멀티 바이트|첫째 바이트가 0이 아닌 경우 및 `c` 의 첫번째 바이트는 0x81\-0x9F 또는 0xE0 –의 범위 내에서 0xFC경우, 두 번째 바이트는 0x40\-0x7E 또는 0x80\-의 범위 내에서 FC입니다.|  
|`_ismbcsymbol`|멀티 바이트 기호|0이 아닌 경우를 반환 하는 경우에만 0x8141\<\=`c`\<\= 0x81AC를 반환합니다.|  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_istlegal`|항상 false를 반환합니다.|`_ismbclegal`|항상 false를 반환합니다.|  
|`_istlegal_l`|항상 false를 반환합니다.|`_ismbclegal_l`|항상 false를 반환합니다.|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_ismbclegal,_ismbclegal_l`|\<mbstring.h\>|  
|`_ismbcsymbol,_ismbcsymbol_l`|\<mbstring.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [\_ismbc 루틴](../../c-runtime-library/ismbc-routines.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)