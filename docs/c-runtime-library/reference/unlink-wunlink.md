---
title: "_unlink, _wunlink | Microsoft Docs"
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
  - "_unlink"
  - "_wunlink"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tunlink"
  - "_unlink"
  - "wunlink"
  - "_wunlink"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tunlink 함수"
  - "_unlink 함수"
  - "_wunlink 함수"
  - "파일[C++], 제거"
  - "파일[C++], 제거"
  - "tunlink 함수"
  - "unlink 함수"
  - "wunlink 함수"
ms.assetid: 5e4f5f1b-1e99-4391-9b18-9ac63c32fae8
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _unlink, _wunlink
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 삭제  
  
## 구문  
  
```  
int _unlink(  
   const char *filename   
);  
int _wunlink(  
   const wchar_t *filename   
);  
```  
  
#### 매개 변수  
 `filename`  
 제거할 파일 이름입니다.  
  
## 반환 값  
 만일 이것이 성공한다면, 이들의 각 함수는 0을 반환합니다.  그렇지 않으면, 함수는 \-1을 반환하고 `errno`를 경로가 읽기 전용 파일을 지정한다는 뜻의 `EACCES`로 설정하거나 파일 또는 경로를 찾을 수 없거나 경로가 디렉터리를 지정한 경우를 의미하는 `ENOENT`으로 설정합니다.  
  
 이러한 반환 코드와 다른 반환코드에 대한 자세한 정보는 [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 를 참조하십시오.  
  
## 설명  
 `_unlink` 함수에는 `filename`에 의해 지정된 파일을 삭제합니다.  `_wunlink`는 `_unlink`의 와이드 문자 버전이며, `_wunlink`의 `filename` 인수는 와이드 문자 문자열입니다.  그렇지 않다면 이러한 함수는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tunlink`|`_unlink`|`_unlink`|`_wunlink`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_unlink`|\<io.h\> 및 \<stdio.h\>|  
|`_wunlink`|\<io.h\> or \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 코드 예제  
 이 프로그램은 CRT\_UNLINK.txt를 삭제 하기 위해 \_unlink을 사용 합니다.  
  
```  
// crt_unlink.c  
  
#include <stdio.h>  
  
int main( void )  
{  
   if( _unlink( "crt_unlink.txt" ) == -1 )  
      perror( "Could not delete 'CRT_UNLINK.TXT'" );  
   else  
      printf( "Deleted 'CRT_UNLINK.TXT'\n" );  
}  
```  
  
### 입력: crt\_unlink.txt  
  
```  
This file will be deleted.  
```  
  
### 샘플 출력  
  
```  
Deleted 'CRT_UNLINK.TXT'  
```  
  
## 해당 .NET Framework 항목  
 [System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [remove, \_wremove](../../c-runtime-library/reference/remove-wremove.md)