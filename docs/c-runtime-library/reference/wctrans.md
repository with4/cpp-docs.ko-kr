---
title: "wctrans | Microsoft Docs"
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
  - "wctrans"
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
  - "wctrans"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "문자 코드, wctrans"
  - "문자, 코드"
  - "문자, 변환"
  - "wctrans 함수"
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# wctrans
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다른 한 세트의 문자 코드 매핑을 결정합니다.  
  
## 구문  
  
```  
wctrans_t wctrans(  
   const char *property   
);  
```  
  
#### 매개 변수  
 `property`  
 잘못 변환 중 하나를 지정 하는 문자열입니다.  
  
## 반환 값  
 현재 로캘의 `LC_CTYPE` 카테고리가 속성 문자열 `property` 과 일치하는 이름의 매핑을 지정하지 않는 경우, 함수는 0을 반환합니다.  그렇지 않으면, [towctrans](../../c-runtime-library/reference/towctrans.md) 에 대한 후속 호출에 두 번째 인수로 사용하기에 적합한 0이 아닌 값을 반환합니다.  
  
## 설명  
 이 함수는 다른 한 세트의 문자 코드 매핑을 결정합니다.  
  
 다음 호출의 쌍은 모든 로캘에서 동일 하게 동작 했지만 "C" 로케일에서도 추가 매핑을 정의할 수 있습니다.  
  
|Function|Same As|  
|--------------|-------------|  
|`tolower(`  `c`  `)`|`towctrans(`  `c` `, wctrans("towlower" ) )`|  
|`towupper(`  `c`  `)`|`towctrans(`  `c` `, wctrans( "toupper" ) )`|  
  
## 요구 사항  
  
|루틴|Required Header|  
|--------|---------------------|  
|`wctrans`|\<wctype.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_wctrans.cpp  
// compile with: /EHsc  
// This example determines a mapping from one set of character  
// codes to another.   
  
#include <wchar.h>  
#include <wctype.h>  
#include <stdio.h>  
#include <iostream>  
  
int main()   
{  
    wint_t c = 'a';  
    printf_s("%d\n",c);  
  
    wctrans_t i = wctrans("toupper");  
    printf_s("%d\n",i);  
  
    wctrans_t ii = wctrans("towlower");  
    printf_s("%d\n",ii);  
  
    wchar_t wc = towctrans(c, i);  
    printf_s("%d\n",wc);  
}  
```  
  
  **97**  
**1**  
**0**  
**65**   
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)