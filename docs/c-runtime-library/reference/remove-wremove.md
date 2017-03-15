---
title: "remove, _wremove | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wremove"
  - "remove"
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
  - "remove"
  - "_wremove"
  - "_tremove"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tremove 함수"
  - "_wremove 함수"
  - "파일[C++], 제거"
  - "파일[C++], 제거"
  - "remove 함수"
  - "tremove 함수"
  - "wremove 함수"
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# remove, _wremove
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 삭제  
  
## 구문  
  
```  
  
      int remove(  
   const char *path   
);  
int _wremove(  
   const wchar_t *path   
);  
```  
  
#### 매개 변수  
 *path*  
 제거될 파일의 경로입니다.  
  
## 반환 값  
 이러한 함수들 각각 파일이 성공적으로 삭제되면 0을 반환합니다.  그렇지 않으면, \-1을 반환하고 `errno` 을 파일이 열거나 읽기 전용 파일을 경로 지정하기 위한 `EACCES` 파일이름 또는 경로를 찾을 수 없을 가리키거나 경로가 디렉터리를 지정하는 **ENOENT**  로 설정합니다.  
  
 이러한 반환 코드와 다른 반환코드에 대한 자세한 정보는 [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 를 참조하십시오.  
  
## 설명  
 **remove** 함수는 *경로* 로 지정된 파일을 제거합니다. `_wremove` 는 **\_remove**의 와이드 문자 버전입니다; `_wremove` 에 대한 *path* 인수는 와이드 문자열입니다.  `_wremove` 와 **\_remove** 동작은 동일하게 작동합니다.  삭제 하기 전에 파일에 모든 핸들을 닫아야 합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_tremove`|**remove**|**remove**|`_wremove`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|**remove**|\<stdio.h\> 또는 \<io.h\>|  
|`_wremove`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_remove.c  
/* This program uses remove to delete crt_remove.txt */  
  
#include <stdio.h>  
  
int main( void )  
{  
   if( remove( "crt_remove.txt" ) == -1 )  
      perror( "Could not delete 'CRT_REMOVE.TXT'" );  
   else  
      printf( "Deleted 'CRT_REMOVE.TXT'\n" );  
}  
```  
  
## 입력: crt\_remove.txt  
  
```  
This file will be deleted.  
```  
  
## 샘플 출력  
  
```  
Deleted 'CRT_REMOVE.TXT'  
```  
  
## 해당 .NET Framework 항목  
 [System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_unlink, \_wunlink](../../c-runtime-library/reference/unlink-wunlink.md)