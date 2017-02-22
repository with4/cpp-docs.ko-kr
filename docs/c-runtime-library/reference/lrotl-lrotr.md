---
title: "_lrotl, _lrotr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lrotl"
  - "_lrotr"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lrotr"
  - "lrotl"
  - "_lrotr"
  - "_lrotl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_lrotl 함수"
  - "_lrotr 함수"
  - "비트"
  - "비트, 회전"
  - "lrotl 함수"
  - "lrotr 함수"
  - "비트 회전"
ms.assetid: d42f295b-35f9-49d2-9ee4-c66896ffe68e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# _lrotl, _lrotr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비트들을 왼쪽으로 \(`_lrotl`\) 또는 오른쪽으로\(`_lrotr`\) 회전합니다.  
  
## 구문  
  
```  
  
      unsigned long _lrotl(  
   unsigned long value,  
   int shift   
);  
unsigned long _lrotr(  
   unsigned long value,  
   int shift   
);  
```  
  
#### 매개 변수  
 *value*  
 회전되는 값입니다.  
  
 `shift`  
 *값*을 이동하기 위한 비트들의 수.  
  
## 반환 값  
 두 함수 모두 회전된 값을 반환 합니다.  반환되는 오류가 없습니다.  
  
## 설명  
 `_lrotl` 와 `_lrotr` 함수들은 `shift` 비트들에 의해 *값* 을 회전시킵니다.  `_lrotl` 는 값을 왼쪽으로 회전합니다.  `_lrotr` 는 값을 오른쪽으로 회전합니다.  두 함수 모두 다른 끝에서 *값* 의 끝으로 회전된 비트들을 래핑합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_lrotl`|\<stdlib.h\>|  
|`_lrotr`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_lrot.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   unsigned long val = 0x0fac35791;  
  
   printf( "0x%8.8lx rotated left eight times is 0x%8.8lx\n",   
            val, _lrotl( val, 8 ) );  
   printf( "0x%8.8lx rotated right four times is 0x%8.8lx\n",   
            val, _lrotr( val, 4 ) );  
}  
```  
  
## Output  
  
```  
0xfac35791 rotated left eight times is 0xc35791fa  
0xfac35791 rotated right four times is 0x1fac3579  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_rotl, \_rotl64, \_rotr, \_rotr64](../../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)