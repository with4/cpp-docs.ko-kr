---
title: "_mkdir, _wmkdir | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wmkdir"
  - "_mkdir"
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
  - "_mkdir"
  - "tmkdir"
  - "_tmkdir"
  - "wmkdir"
  - "_wmkdir"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mkdir 함수"
  - "_tmkdir 함수"
  - "_wmkdir 함수"
  - "디렉터리[C++], 만들기"
  - "폴더[C++], 만들기"
  - "mkdir 함수"
  - "tmkdir 함수"
  - "wmkdir 함수"
ms.assetid: 7f22d01d-63a5-4712-a6e7-d34878b2d840
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _mkdir, _wmkdir
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

새 디렉터리를 만듭니다.  
  
## 구문  
  
```  
  
      int _mkdir(  
   const char *dirname   
);  
int _wmkdir(  
   const wchar_t *dirname   
);  
```  
  
#### 매개 변수  
 `dirname`  
 새 디렉터리에 대 한 경로  
  
## 반환 값  
 이러한 함수들은 새 디렉터리가 만들어진 경우 값 0을 반환합니다.  오류가 발생하면, 함수는 \-1을 반환하고 `errno` 다음과 같이 세팅합니다.  
  
 `EEXIST`  
 `dirname`가 기존 파일, 디렉터리, 장치 이름일 경우 디렉터리는 생성되지 않습니다.  
  
 `ENOENT`  
 경로을\(를\) 찾을 수 없습니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_mkdir`함수는 *dirname.*으로 지정된 새 디렉터리를 만듭니다. `_mkdir` 은 호출당 하나의 새 디렉터리를 만들 수 있고 마지막 요소는 `dirname`은 새 디렉터리 이름으로 지정됩니다.  `_mkdir`경로 구분 기호를 변환하지 않습니다.  Windows NT에서 백슬래시 \(\\\)와 슬래시 \(\/\)는 런타임 루틴에 문자열에 유효한 경로 구분 기호입니다.  
  
 `_wmkdir`는 `_mkdir`의 와이드 문자 버전이며, `_wmkdir`의 `dirname` 인수는 와이드 문자 문자열입니다.  `_wmkdir` 및 `_mkdir` 는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tmkdir`|`_mkdir`|`_mkdir`|`_wmkdir`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_mkdir`|\<direct.h\>|  
|`_wmkdir`|\<direct.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_makedir.c  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   if( _mkdir( "\\testtmp" ) == 0 )  
   {  
      printf( "Directory '\\testtmp' was successfully created\n" );  
      system( "dir \\testtmp" );  
      if( _rmdir( "\\testtmp" ) == 0 )  
        printf( "Directory '\\testtmp' was successfully removed\n"  );  
      else  
         printf( "Problem removing directory '\\testtmp'\n" );  
   }  
   else  
      printf( "Problem creating directory '\\testtmp'\n" );  
}  
```  
  
## 샘플 출력  
  
```  
Directory '\testtmp' was successfully created  
 Volume in drive C has no label.  
 Volume Serial Number is E078-087A  
  
 Directory of C:\testtmp  
  
02/12/2002  09:56a      <DIR>          .  
02/12/2002  09:56a      <DIR>          ..  
               0 File(s)              0 bytes  
               2 Dir(s)  15,498,690,560 bytes free  
Directory '\testtmp' was successfully removed  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::IO::Directory::CreateDirectory](https://msdn.microsoft.com/en-us/library/system.io.directory.createdirectory.aspx)  
  
-   [System::IO::DirectoryInfo::CreateSubdirectory](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.createsubdirectory.aspx)  
  
## 참고 항목  
 [디렉터리 제어](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)