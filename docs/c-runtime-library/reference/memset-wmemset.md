---
title: "memset, wmemset | Microsoft Docs"
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
  - "wmemset"
  - "memset"
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
  - "memset"
  - "wmemset"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "memset 함수"
  - "wmemset 함수"
ms.assetid: e7ceb01b-df69-49c2-b294-a39358ad4699
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# memset, wmemset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 문자로 버퍼를 설정합니다.  
  
## 구문  
  
```  
  
      void *memset(  
   void *dest,  
   int c,  
   size_t count   
);  
wchar_t *wmemset(  
   wchar_t *dest,  
   wchar_t c,  
   size_t count  
);  
```  
  
#### 매개 변수  
 *대상*  
 대상에 대한 포인터입니다.  
  
 `c`  
 설정할 문자입니다.  
  
 *count*  
 문자들의 수.  
  
## 반환 값  
 `dest`의 값입니다.  
  
## 설명  
 `dest` 의 첫번째 `count` 문자를 문자 `c` 로 설정합니다.  
  
 **보안 정보** 대상 버퍼에 적어도 `count` 문자 만큼 충분한 공간이 있는지 확인합니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`memset`|\<memory.h\> 또는 \<string.h\>|  
|`wmemset`|\<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_memset.c  
/* This program uses memset to  
 * set the first four chars of buffer to "*".  
 */  
  
#include <memory.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char buffer[] = "This is a test of the memset function";  
  
   printf( "Before: %s\n", buffer );  
   memset( buffer, '*', 4 );  
   printf( "After:  %s\n", buffer );  
}  
```  
  
## Output  
  
```  
Before: This is a test of the memset function  
After:  **** is a test of the memset function  
```  
  
 Wmemset의 사용 예는 다음과 같습니다.  
  
```  
// crt_wmemset.c  
/* This program uses memset to  
 * set the first four chars of buffer to "*".  
 */  
  
#include <wchar.h>  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buffer[] = L"This is a test of the wmemset function";  
  
   wprintf( L"Before: %s\n", buffer );  
   wmemset( buffer, '*', 4 );  
   wprintf( L"After:  %s\n", buffer );  
}  
```  
  
## Output  
  
```  
Before: This is a test of the wmemset function  
After:  **** is a test of the wmemset function  
```  
  
## 해당 .NET Framework 항목  
 [System::Buffer::SetByte](https://msdn.microsoft.com/en-us/library/system.buffer.setbyte.aspx)  
  
## 참고 항목  
 [버퍼 조작](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)