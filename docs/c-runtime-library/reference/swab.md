---
title: "_swab | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_swab"
  - "stdlib/_swab"
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
  - "_swab"
  - "stdlib/_swab"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_swab 함수"
  - "바이트, 스와핑"
  - "swab 함수"
  - "바이트 스와핑"
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _swab
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

바이트 바꾸기  
  
## 구문  
  
```  
void _swab(  
   char *src,  
   char *dest,  
   int n   
);  
```  
  
#### 매개 변수  
 `src`  
 데이터를 복사하고 바꿨습니다.  
  
 `dest`  
 교체 된 데이터에 대한 저장소 위치입니다.  
  
 `n`  
 복사하고 바뀐 바이트의 수  
  
## 설명  
 `n` 가 짝수인 경우 `_swab` 함수는 `src` 에서 `n` 바이트를 복사하고 인접한 바이트의 각 쌍을 교체하고 `dest` 에 결과를 저장합니다.  `n` 이 홀수 인 경우 `_swab` 은 `src` 의 첫 번째 `n-1` 바이트를 복사하고 바꿉니다.  `_swab`은 이진 데이터를 서로 다른 바이트 순서를 사용 하는 컴퓨터로 전송할 때 주로 사용 됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_swab`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_swab.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";  
char to[] =   "..........................";  
  
int main()  
{  
    printf( "Before: %s\n        %s\n\n", from, to );  
    _swab( from, to, sizeof( from ) );  
    printf( "After:  %s\n        %s\n\n", from, to );  
}  
```  
  
  **Before: BADCFEHGJILKNMPORQTSVUXWZY**  
 **..........................**  
**After:  BADCFEHGJILKNMPORQTSVUXWZY**  
 **ABCDEFGHIJKLMNOPQRSTUVWXYZ**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [버퍼 조작](../../c-runtime-library/buffer-manipulation.md)