---
title: "_rotl, _rotl64, _rotr, _rotr64 | Microsoft Docs"
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
  - "_rotr64"
  - "_rotl"
  - "_rotr"
  - "_rotl64"
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
  - "_rotr64"
  - "rotl64"
  - "_rotl64"
  - "rotr64"
  - "rotr"
  - "_rotr"
  - "_rotl"
  - "rotl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_rotl 함수"
  - "_rotl64 함수"
  - "_rotr 함수"
  - "_rotr64 함수"
  - "비트, 회전"
  - "비트 회전"
  - "rotl 함수"
  - "rotl64 함수"
  - "rotr 함수"
  - "rotr64 함수"
ms.assetid: cfce439b-366f-4584-8ab1-d527b13fcfc6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _rotl, _rotl64, _rotr, _rotr64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비트들을 왼쪽으로 \(`_rotl`\) 또는 오른쪽으로\(`_rotr`\) 회전합니다.  
  
## 구문  
  
```  
  
      unsigned int _rotl(  
   unsigned int value,  
   int shift   
);  
unsigned __int64 _rotl64(  
   unsigned __int64 value,   
   int shift  
);  
unsigned int _rotr(  
   unsigned int value,  
   int shift   
);  
unsigned __int64 _rotr64(  
   unsigned __int64 value,  
   int shift  
);  
```  
  
#### 매개 변수  
 *value*  
 회전되는 값입니다.  
  
 `shift`  
 이동할 비트 수입니다.  
  
## 반환 값  
 회전된 값입니다.  반환되는 오류가 없습니다.  
  
## 설명  
 `_rotl` 와 `_rotr` 함수들은 부호가 없는 *값* 을 `shift` 비트들에 의해 회전시킵니다.  `_rotl` 는 값을 왼쪽으로 회전합니다.  `_rotr` 는 값을 오른쪽으로 회전합니다.  두 함수 모두 다른 끝에서 *값* 의 끝으로 회전된 비트들을 래핑합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|**\_rotl, \_rotl64**|\<stdlib.h\>|  
|**\_rotr, \_rotr64**|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_rot.c  
/* This program shifts values to rotate an integer.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   unsigned val = 0x0fd93;  
   __int64 val2 = 0x0101010101010101;  
  
   printf( "0x%4.4x rotated left three times is 0x%4.4x\n",   
           val, _rotl( val, 3 ) );  
   printf( "0x%4.4x rotated right four times is 0x%4.4x\n",   
           val, _rotr( val, 4 ) );  
  
   printf( "%I64x rotated left three times is %I64x\n",  
           val2, _rotl64( val2, 3 ) );  
   printf( "%I64x rotated right four times is %I64x\n",   
           val2, _rotr64( val2, 4 ) );  
}  
```  
  
## Output  
  
```  
0xfd93 rotated left three times is 0x7ec98  
0xfd93 rotated right four times is 0x30000fd9  
101010101010101 rotated left three times is 808080808080808  
101010101010101 rotated right four times is 1010101010101010  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_lrotl, \_lrotr](../../c-runtime-library/reference/lrotl-lrotr.md)