---
title: "_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbcpunct_l"
  - "_ismbcblank"
  - "_ismbcprint"
  - "_ismbcgraph_l"
  - "_ismbcblank_l"
  - "_ismbcpunct"
  - "_ismbcprint_l"
  - "_ismbcspace_l"
  - "_ismbcspace"
  - "_ismbcgraph"
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
  - "_ismbcspace"
  - "_ismbcgraph"
  - "_ismbcpunct"
  - "ismbcspace_l"
  - "ismbcgraph"
  - "_ismbcgraph_l"
  - "_ismbcprint"
  - "_ismbcspace_l"
  - "ismbcprint"
  - "ismbcgraph_l"
  - "ismbcspace"
  - "ismbcpunct"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbcgraph 함수"
  - "_ismbcgraph_l 함수"
  - "_ismbcprint 함수"
  - "_ismbcprint_l 함수"
  - "_ismbcpunct 함수"
  - "_ismbcpunct_l 함수"
  - "_ismbcspace 함수"
  - "_ismbcspace_l 함수"
  - "ismbcgraph 함수"
  - "ismbcgraph_l 함수"
  - "ismbcprint 함수"
  - "ismbcprint_l 함수"
  - "ismbcpunct 함수"
  - "ismbcpunct_l 함수"
  - "ismbcspace 함수"
  - "ismbcspace_l 함수"
ms.assetid: 8e0a5f47-ba64-4411-92a3-3c525d16e3be
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자 그래픽 문자, 표시 문자, 문장 부호, 문자 또는 공백 문자인지 확인합니다.  
  
> [!IMPORTANT]
>  이 API는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은[\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _ismbcgraph(  
   unsigned int c   
);  
int _ismbcgraph_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcprint(  
   unsigned int c   
);  
int _ismbcprint_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcpunct(  
   unsigned int c  
);  
int _ismbcpunct_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcblank(  
   unsigned int c   
);  
int _ismbcblank_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcspace(  
   unsigned int c   
);  
int _ismbcspace_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `c`  
 결정할 문자입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 이러한 각 루틴은 이 문자가 테스트 조건을 만족하는 경우, 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다.   `c`  \<\= 255 및 해당 하는  `_ismbb`  루틴인 경우 \(예를 들어,  `_ismbcalnum`  에 반응하는   `_ismbbalnum` \), 결과는   `_ismbb`  루틴에 응답하는 반환값 입니다.  
  
 이 `_l` 접미사가 있는 이러한 함수 버전은 로캘 종속 동작에 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
## 설명  
 이러한 각 함수는 지정한 조건에 대해 주어진 멀티바이트 문자를 테스트합니다.  
  
|루틴|테스트 조건|932 코드 페이지 예제|  
|--------|------------|-------------------|  
|`_ismbcgraph`|그래픽|이 `c` 는 공백 \( \)을 제외한 모든 ASCII 또는 가타카나 인쇄 가능한 문자의 싱글 바이트 표현의 경우에만 반환 값이 0이 아닙니다.|  
|`_ismbcprint`|인쇄 가능|이 `c` 는 공백 \( \)을 포함한 모든 ASCII 또는 가타카나 인쇄 가능한 문자의 싱글 바이트 표현의 경우에만 반환 값이 0이 아닙니다.|  
|`_ismbcpunct`|문장 부호|이 `c` 는 표현 싱글바이트 가타카나 또는 문장 부호 문자인 경우 반환 값이 0이 아닙니다.|  
|`_ismbcblank`|스페이스나 수평 탭|이 `c` 는 공백 문자 또는 수평 탭 문자인 경우 0이 아닌 값을 반환합니다 : `c`\=0x20 or `c`\=0x09.|  
|`_ismbcspace`|공백|이 `c` 는 공백 문자인 경우 0이 아닌 값을 반환합니다 : `c`\=0x20 or 0x09\<\=`c`\<\=0x0D.|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_ismbcgraph`|\<mbstring.h\>|  
|`_ismbcgraph_l`|\<mbstring.h\>|  
|`_ismbcprint`|\<mbstring.h\>|  
|`_ismbcprint_l`|\<mbstring.h\>|  
|`_ismbcpunct`|\<mbstring.h\>|  
|`_ismbcpunct_l`|\<mbstring.h\>|  
|`_ismbcblank`|\<mbstring.h\>|  
|`_ismbcblank_l`|\<mbstring.h\>|  
|`_ismbcspace`|\<mbstring.h\>|  
|`_ismbcspace_l`|\<mbstring.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
  
-   [System::Char::IsPunctuation](https://msdn.microsoft.com/en-us/library/system.char.ispunctuation.aspx)  
  
-   [System::Char::IsWhiteSpace](https://msdn.microsoft.com/en-us/library/system.char.iswhitespace.aspx)  
  
-   이 `_ismbcgraph` 와 `_ismbcprint` 에 대해 : 적용할 수 없습니다. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_ismbc 루틴](../../c-runtime-library/ismbc-routines.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)   
 [\_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)