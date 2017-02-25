---
title: "memmove_s, wmemmove_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wmemmove_s"
  - "memmove_s"
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
  - "wmemmove_s"
  - "memmove_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memmove_s 함수"
  - "wmemmove_s 함수"
ms.assetid: a17619e4-1307-4bb0-98c6-77f8c68dab2d
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# memmove_s, wmemmove_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다른 하나의 버퍼를 이동합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md) 버전입니다.  
  
## 구문  
  
```  
  
      errno_t memmove_s(  
   void *dest,  
   size_t numberOfElements,  
   const void *src,  
   size_t count  
);  
errno_t wmemmove_s(  
   wchar_t *dest,  
   size_t numberOfElements,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### 매개 변수  
 `dest`  
 대상 개체입니다.  
  
 `numberOfElements`  
 대상 버퍼의 크기입니다.  
  
 `src`  
 개체 소스  
  
 `count`  
 복사할 바이트 수 \(`memmove_s`\) 또는 문자 \(`wmemmove_s`\) 입니다.  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
### 오류 조건  
  
|`dest`|`numberOfElements`|`src`|반환 값|`dest`의 내용입니다.|  
|------------|------------------------|-----------|----------|--------------------|  
|`NULL`|any|any|`EINVAL`|수정 안 됨|  
|any|any|`NULL`|`EINVAL`|수정 안 됨|  
|any|\< `count`|any|`ERANGE`|수정 안 됨|  
  
## 설명  
 문자들의 `count` 바이트들은 `src` 부터 `dest`*.*를 복사합니다. 원본 영역과 대상의 일부 영역이 겹치는 경우, `memmove_s`는 모두 겹치는 영역에서 원본 소스 바이트가 덮어쓰기 전에 복사되는지 확인합니다.  
  
 만일 `dest` 또는 `src` 가 null 포인터 이거나 대상 문자열이 너무 작으면, 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `EINVAL`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`memmove_s`|\<string.h\>|  
|`wmemmove_s`|\<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_memmove_s.c  
//  
// The program demonstrates the   
// memmove_s function which works as expected  
// for moving overlapping regions.  
  
#include <stdio.h>  
#include <string.h>  
  
int main()  
{  
   char str[] = "0123456789";  
  
   printf("Before: %s\n", str);  
  
   // Move six bytes from the start of the string  
   // to a new position shifted by one byte. To protect against  
   // buffer overrun, the secure version of memmove requires the  
   // the length of the destination string to be specified.   
  
   memmove_s((str + 1), strnlen(str + 1, 10), str, 6);   
  
   printf_s(" After: %s\n", str);  
}  
```  
  
## Output  
  
```  
Before: 0123456789  
 After: 0012345789  
```  
  
## 해당 .NET Framework 항목  
 [System::Buffer::BlockCopy](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx)  
  
## 참고 항목  
 [버퍼 조작](../../c-runtime-library/buffer-manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)