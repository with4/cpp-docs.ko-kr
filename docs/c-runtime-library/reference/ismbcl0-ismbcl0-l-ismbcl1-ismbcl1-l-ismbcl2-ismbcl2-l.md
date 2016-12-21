---
title: "_ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l | Microsoft Docs"
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
  - "_ismbcl2"
  - "_ismbcl1"
  - "_ismbcl0"
  - "_ismbcl2_l"
  - "_ismbcl1_l"
  - "_ismbcl0_l"
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
  - "ismbcl0"
  - "_ismbcl1_l"
  - "_ismbcl0"
  - "ismbcl1"
  - "ismbcl0_l"
  - "_ismbcl2_l"
  - "ismbcl2"
  - "ismbcl1_l"
  - "_ismbcl1"
  - "_ismbcl0_l"
  - "_ismbcl2"
  - "ismbcl2_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ismbcl0 함수"
  - "_ismbcl0_l 함수"
  - "_ismbcl1 함수"
  - "_ismbcl1_l 함수"
  - "_ismbcl2 함수"
  - "_ismbcl2_l 함수"
  - "ismbcl0 함수"
  - "ismbcl0_l 함수"
  - "ismbcl1 함수"
  - "ismbcl1_l 함수"
  - "ismbcl2 함수"
  - "ismbcl2_l 함수"
ms.assetid: ee15ebd1-462c-4a43-95f3-6735836d626a
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ismbcl0, _ismbcl0_l, _ismbcl1, _ismbcl1_l, _ismbcl2, _ismbcl2_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**코드 페이지 932 특유의 기능**, 현재 로캘에 지정된 LC\_CTYPE 변환 상태 범주를 사용합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _ismbcl0(  
   unsigned int c   
);  
int _ismbcl0_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcl1(  
   unsigned int c   
);  
int _ismbcl1_l(  
   unsigned int c ,  
   _locale_t locale  
);  
int _ismbcl2(  
   unsigned int c   
);  
int _ismbcl2_l(  
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
 이러한 각 루틴은 이 문자가 테스트 조건을 만족하는 경우 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다.   `c`  \<\= 255 및 해당 하는  `_ismbb`  루틴인 경우 \(예를 들어,  `_ismbcalnum`  에 반응하는   `_ismbbalnum` \), 결과는   `_ismbb`  루틴에 응답하는 반환값 입니다.  
  
## 설명  
 이러한 각 함수는 지정한 조건에 대해 주어진 멀티바이트 문자를 테스트합니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  `_l` 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, `_l` 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다.  자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
|루틴|테스트 조건 \(코드 페이지 932만\)|  
|--------|----------------------------|  
|`_ismbcl0`|JIS non\-Kanji: 0x8140\<\=`c`\<\=0x889E.|  
|`_ismbcl0_l`|JIS non\-Kanji: 0x8140\<\=`c`\<\=0x889E.|  
|`_ismbcl1`|JIS level\-1: 0x889F\<\=`c`\<\=0x9872.|  
|`_ismbcl1_l`|JIS level\-1: 0x889F\<\=`c`\<\=0x9872.|  
|`_ismbcl2`|JIS level\-2: 0x989F\<\=`c`\<\=0xEAA4.|  
|`_ismbcl2_l`|JIS level\-2: 0x989F\<\=`c`\<\=0xEAA4.|  
  
 함수는 그 이상 묘사된 테스트 조건에 일치하는 지정된 값 `c` 을 검사하지만, `c` 이 유효한 멀티 바이트 문자임을 검사하지 않습니다.  하위 바이트 0xFF, 0x00 – 0x7F 0x3F, 0xFD – 범위에는 이러한 함수 문자 테스트 조건에 맞는 것을 나타내는 0이 아닌 값을 반환합니다.  정의된 벌티 바이트인지 테스트하는 [\_ismbbtrail](../../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md) 사용하세요.  
  
 **최종 코드 페이지 932 관련**  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_ismbcl0`|\<mbstring.h\>|  
|`_ismbcl0_l`|\<mbstring.h\>|  
|`_ismbcl1`|\<mbstring.h\>|  
|`_ismbcl1_l`|\<mbstring.h\>|  
|`_ismbcl2`|\<mbstring.h\>|  
|`_ismbcl2_l`|\<mbstring.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [문자 분류](../../c-runtime-library/character-classification.md)   
 [\_ismbc 루틴](../../c-runtime-library/ismbc-routines.md)   
 [is, isw 루틴](../../c-runtime-library/is-isw-routines.md)