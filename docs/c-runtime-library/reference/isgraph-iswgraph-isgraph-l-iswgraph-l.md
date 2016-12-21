---
title: "isgraph, iswgraph, _isgraph_l, _iswgraph_l | Microsoft Docs"
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
  - "isgraph"
  - "iswgraph"
  - "_iswgraph_l"
  - "_isgraph_l"
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
  - "_isgraph_l"
  - "_iswgraph_l"
  - "_ismbcgraph_l"
  - "Isgraph"
  - "_istgraph_l"
  - "_istgraph"
  - "iswgraph"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_isgraph_l 함수"
  - "_ismbcgraph_l 함수"
  - "_istgraph 함수"
  - "_istgraph_l 함수"
  - "_iswgraph_l 함수"
  - "isgraph 함수"
  - "istgraph 함수"
  - "iswgraph 함수"
ms.assetid: 531a5f34-4302-4d0a-8a4f-b7ea150ad941
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isgraph, iswgraph, _isgraph_l, _iswgraph_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정수가 빈 문자를 나타내는지 여부를 확인합니다.  
  
## 구문  
  
```  
int isgraph(  
   int c   
);  
int iswgraph(  
   wint_t c   
);  
int _isgraph_l(  
   int c,  
   _locale_t locale  
);  
int _iswgraph_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 정수입니다.  
  
## 반환 값  
 `c` 가 인쇄 가능한 공백 이외의 캐릭터의 특정 표현일 경우, 이러한 루틴의 각각은 0이 아닌 경우를 반환 합니다.  `isgraph` 경우 0이 아닌 값을 반환 합니다. `c` 공백 이외의 인쇄 가능한 문자입니다.  `iswgraph` 경우 0이 아닌 값을 반환 합니다. `c` 와이드 문자 공백 이외의 넓은 인쇄 가능한 문자입니다.  만약 `c` 가 테스트 조건을 만족하지 않는 경우 각각의 이러한 루틴은 0을 반환합니다.  
  
 여기서 `_l` 접미사가 있는 이러한 함수의 버전은 로캘 종속 동작에 대해 현재 로캘 대신 전달된 로캘을 사용합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 여기서 `isgraph` 와 `_isgraph_l` 의 동작이 정의되지 않음을 의미합니다. 이는 `c` 가 EOF가 아니거나 0부터 0xFF 내에 포함되지 않는 경우입니다.  디버그 CRT 라이브러리가 사용되고 `c`가 이들 값 중 하나가 아니면 함수에 어설션이 발생합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_istgraph`|`isgraph`|[\_ismbcgraph](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswgraph`|  
|`_istgraph_l`|`_isgraph_l`|[\_ismbcgraph\_l](../../c-runtime-library/reference/ismbcgraph-functions.md)|`_iswgraph_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`isgraph`|\<ctype.h\>|  
|`iswgraph`|\<ctype.h\> 또는 \<wchar.h\>|  
|`_isgraph_l`|\<ctype.h\>|  
|`_iswgraph_l`|\<ctype.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)