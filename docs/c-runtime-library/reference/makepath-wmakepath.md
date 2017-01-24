---
title: "_makepath, _wmakepath | Microsoft Docs"
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
  - "_makepath"
  - "_wmakepath"
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
  - "_wmakepath"
  - "_tmakepath"
  - "makepath"
  - "tmakepath"
  - "wmakepath"
  - "_makepath"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_makepath 함수"
  - "_tmakepath 함수"
  - "_wmakepath 함수"
  - "makepath 함수"
  - "경로"
  - "tmakepath 함수"
  - "wmakepath 함수"
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _makepath, _wmakepath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구성 요소에서 경로 이름을 생성합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)를 참조하십시오.  
  
## 구문  
  
```  
void _makepath(  
   char *path,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
void _wmakepath(  
   wchar_t *path,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
```  
  
#### 매개 변수  
 `path`  
 전체 경로 버퍼입니다.  
  
 `drive`  
 원하는 드라이브에 따른 문자\(A, B, 등등\)와 선택적인 뒤의 콜론을 포함합니다.  `_makepath`는 복합 경로에 콜론이 누락되었다면 이를 자동으로 삽입합니다.  `drive`가 `NULL` 또는 빈 문자열을 가리키면, 복합 `path` 문자열에는 드라이브 문자가 나타나지 않습니다.  
  
 `dir`  
 드라이브 지정자 또는 실제 파일 이름을 제외한 디렉터리의 경로를 포함합니다.  후행 슬래시는 선택적이며 슬래시 \(\/\) 또는 백슬래시 \(\\\) 중 하나 또는 둘 모두 `dir` 인수에 사용할 수 있습니다.  뒤에 후행 슬래시 \(\/ 또는 \\\)가 지정되지 않으면, 자동적으로 삽입됩니다.  `dir`가 `NULL` 또는 빈 문자열을 가리키는 경우, 복합 `path` 문자열에 디렉터리 경로가 삽입되지 않습니다.  
  
 `fname`  
 파일 이름 확장명이 없는 기본 파일 이름을 포함합니다.  `fname`가 `NULL` 또는 빈 문자열을 가리키면, 복합 `path` 문자열에 파일 이름이 삽입되지 않습니다.  
  
 `ext`  
 앞의 마침표\(.\)를 포함하거나 포함하지 않은 실제 파일 이름 확장명을 포함합니다.  `_makepath`는 `ext`에 마침표가 나타나지 않은 경우 자동으로 이를 삽입합니다.  `ext`가 `NULL` 또는 빈 문자열을 가리키면, 복합 `path` 문자열에 확장명이 삽입되지 않습니다.  
  
## 설명  
 `_makepath` 함수는 개별 구성요소에서 복합 경로 문자열을 생성하고 `path`에 결과를 저장합니다.  `path`는 드라이브 문자, 디렉터리 경로, 파일 이름 및 파일 이름 확장명을 포함할 수 있습니다.  `_wmakepath`는 `_makepath`의 와이드 문자 버전이며, `_wmakepath`에 대한 인수는 와이드 문자 문자열입니다.  `_wmakepath` 및 `_makepath` 는 동일하게 작동합니다.  
  
 **Security Note**는 null로 끝나는 문자열을 사용 합니다.  버퍼 오버런을 피하기 위해 null로 끝나는 문자열은 `path` 버퍼의 크기를 초과 하지 않아야만 합니다.  `_makepath`는 복합 경로 문자열의 길이가 `_MAX_PATH`를 넘지 않도록 보장하지 않습니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tmakepath`|`_makepath`|`_makepath`|`_wmakepath`|  
  
 `path` 인수는 반드시 전체 경로를 포함하기에 충분히 큰 빈 버퍼를 가리켜야 합니다.  복합 `path`는 반드시 Stdlib.h에 정의된 `_MAX_PATH` 상수보다 더 크지 않아야 합니다.  
  
 경로가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  또한, `errno`는 `EINVAL`로 설정됩니다.  `NULL`값은 다른 모든 매개 변수에 대해 허용됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_makepath`|\<stdlib.h\>|  
|`_wmakepath`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_makepath.c  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
  
   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996  
   // Note: _makepath is deprecated; consider using _makepath_s instead  
   printf( "Path created with _makepath: %s\n\n", path_buffer );  
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996  
   // Note: _splitpath is deprecated; consider using _splitpath_s instead  
   printf( "Path extracted with _splitpath:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
  **Path created with \_makepath: c:\\sample\\crt\\makepath.c**  
**Path extracted with \_splitpath:**  
 **Drive: c:**  
 **Dir: \\sample\\crt\\**  
 **Filename: makepath**  
 **Ext: .c**   
## 해당 .NET Framework 항목  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)