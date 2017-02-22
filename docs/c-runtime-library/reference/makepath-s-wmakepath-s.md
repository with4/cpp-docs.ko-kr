---
title: "_makepath_s, _wmakepath_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wmakepath_s"
  - "_makepath_s"
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
  - "_wmakepath_s"
  - "makepath_s"
  - "_makepath_s"
  - "wmakepath_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_makepath_s 함수"
  - "wmakepath_s 함수"
  - "경로"
  - "_wmakepath_s 함수"
  - "makepath_s 함수"
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# _makepath_s, _wmakepath_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구성 요소에서 경로 이름을 생성합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md) 버전입니다.  
  
## 구문  
  
```  
errno_t _makepath_s(  
   char *path,  
   size_t sizeInBytes,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
errno_t _wmakepath_s(  
   wchar_t *path,  
   size_t sizeInWords,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
template <size_t size>  
errno_t _makepath_s(  
   char (&path)[size],  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
); // C++ only  
template <size_t size>  
errno_t _wmakepath_s(  
   wchar_t (&path)[size],  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
); // C++ only  
```  
  
#### 매개 변수  
 \[out\] `path`  
 전체 경로 버퍼입니다.  
  
 \[in\] `sizeInWords`  
 단어에서 버퍼의 크기입니다.  
  
 \[in\] `sizeInBytes`  
 버퍼의 크기\(바이트\)입니다.  
  
 \[in\] `drive`  
 원하는 드라이브에 따른 문자\(A, B, 등등\)와 선택적인 뒤의 콜론을 포함합니다.  `_makepath_s`는 복합 경로에 콜론이 누락되었다면 이를 자동으로 삽입합니다.  `drive`가 `NULL` 또는 빈 문자열을 가리키면, 복합 `path` 문자열에는 드라이브 문자가 나타나지 않습니다.  
  
 \[in\] `dir`  
 드라이브 지정자 또는 실제 파일 이름을 제외한 디렉터리의 경로를 포함합니다.  후행 슬래시는 선택적이며 슬래시 \(\/\) 또는 백슬래시 \(\\\) 중 하나 또는 둘 모두 `dir` 인수에 사용할 수 있습니다.  뒤에 후행 슬래시 \(\/ 또는 \\\)가 지정되지 않으면, 자동적으로 삽입됩니다.  `dir`가 `NULL` 또는 빈 문자열을 가리키는 경우, 복합 `path` 문자열에 디렉터리 경로가 삽입되지 않습니다.  
  
 \[in\] `fname`  
 파일 이름 확장명이 없는 기본 파일 이름을 포함합니다.  `fname`가 `NULL` 또는 빈 문자열을 가리키면, 복합 `path` 문자열에 파일 이름이 삽입되지 않습니다.  
  
 \[in\] `ext`  
 앞의 마침표\(.\)를 포함하거나 포함하지 않은 실제 파일 이름 확장명을 포함합니다.  `_makepath_s`는 `ext`에 마침표가 나타나지 않은 경우 자동으로 이를 삽입합니다.  `ext`가 `NULL` 또는 빈 문자열을 가리키면, 복합 `path` 문자열에 확장명이 삽입되지 않습니다.  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
### 오류 조건  
  
|`path`|`sizeInWords` \/ `sizeInBytes`|반환|`path`의 내용입니다.|  
|------------|------------------------------------|--------|--------------------|  
|`NULL`|any|`EINVAL`|수정 안 됨|  
|any|\<\= 0|`EINVAL`|수정 안 됨|  
  
 위의 오류 조건이 발생하는 경우, 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  실행이 계속되도록 허용된 경우, `errno`는 `EINVAL` 로 설정되고 함수는 `EINVAL`를 반환합니다. `NULL` 은 `drive`, `fname`, 및 `ext` 에 대해 허용됩니다.  매개 변수가 null 포인터거나 빈 문자열인 경우에 작동에 대한 자세한 정보는 설명 부분을 참조하십시오.  
  
## 설명  
 `_makepath_s` 함수는 개별 구성요소에서 복합 경로 문자열을 생성하고 `path`에 결과를 저장합니다.  `path`는 드라이브 문자, 디렉터리 경로, 파일 이름 및 파일 이름 확장명을 포함할 수 있습니다.  `_wmakepath_s`는 `_makepath_s`의 와이드 문자 버전이며, `_wmakepath_s`에 대한 인수는 와이드 문자 문자열입니다.  `_wmakepath_s` 및 `_makepath_s` 는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tmakepath_s`|`_makepath_s`|`_makepath_s`|`_wmakepath_s`|  
  
 `path` 인수는 반드시 전체 경로를 포함하기에 충분히 큰 빈 버퍼를 가리켜야 합니다.  복합 `path`는 반드시 Stdlib.h에 정의된 `_MAX_PATH` 상수보다 더 크지 않아야 합니다.  
  
 경로가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  또한, `errno`는 `EINVAL`로 설정됩니다.  `NULL`값은 다른 모든 매개 변수에 대해 허용됩니다.  
  
 C\+\+에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며\(크기 인수를 지정할 필요가 없어짐\), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_makepath_s`|\<stdlib.h\>|  
|`_wmakepath_s`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_makepath_s.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
   errno_t err;  
  
   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",  
                      "crt_makepath_s", "c" );  
   if (err != 0)  
   {  
      printf("Error creating path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );  
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,  
                       _MAX_FNAME, ext, _MAX_EXT );  
   if (err != 0)  
   {  
      printf("Error splitting the path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path extracted with _splitpath_s:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
## Output  
  
```  
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c  
  
Path extracted with _splitpath_s:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: crt_makepath_s  
  Ext: .c  
```  
  
## 해당 .NET Framework 항목  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)