---
title: "_memccpy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_memccpy"
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
  - "_memccpy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_memccpy 함수"
  - "memccpy 함수"
ms.assetid: 9a2337df-6e85-4eba-b247-dd0532f45ddb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _memccpy
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

버퍼에서 문자를 복사합니다.  
  
## 구문  
  
```  
  
      void *_memccpy(  
   void *dest,  
   const void *src,  
   int c,  
   size_t count   
);  
```  
  
#### 매개 변수  
 *대상*  
 목적지에 대한 포인터입니다.  
  
 *src*  
 소스에 대한 포인터입니다.  
  
 `c`  
 복사할 마지막 문자입니다.  
  
 *count*  
 문자들의 수.  
  
## 반환 값  
 만일 문자 `c` 가 복사된 경우, `_memccpy` 해당 문자의 바로 뒤에 *대상* 에서 char로 포인터를 반환합니다.  만일 `c` 가 복사되지 않은 경우, 이것은 **NULL**을 반환합니다.  
  
## 설명  
 `_memccpy` 함수는 문자 `c` 가 복사되었거나 *count* 문자들이 복사되었을 때, 이들이 처음 올때마다 *대상* 의 멈춤으로 *src* 의  0개 이상의 문자들을 복사합니다.  
  
 **보안 정보** 는 원본 버퍼보다 크거나 같은 크기의 대상 버퍼인지 확인합니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_memccpy`|\<memory.h\> 또는 \<string.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_memccpy.c  
  
#include <memory.h>  
#include <stdio.h>  
#include <string.h>  
  
char string1[60] = "The quick brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char buffer[61];  
   char *pdest;  
  
   printf( "Function: _memccpy 60 characters or to character 's'\n" );  
   printf( "Source: %s\n", string1 );  
   pdest = _memccpy( buffer, string1, 's', 60 );  
   *pdest = '\0';  
   printf( "Result: %s\n", buffer );  
   printf( "Length: %d characters\n", strlen( buffer ) );  
}  
```  
  
## Output  
  
```  
Function: _memccpy 60 characters or to character 's'  
Source: The quick brown dog jumps over the lazy fox  
Result: The quick brown dog jumps  
Length: 25 characters  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::Buffer::BlockCopy](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx)  
  
-   [System::String::Copy](https://msdn.microsoft.com/en-us/library/system.string.copy.aspx)  
  
## 참고 항목  
 [버퍼 조작](../../c-runtime-library/buffer-manipulation.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)