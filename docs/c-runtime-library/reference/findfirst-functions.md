---
title: "_findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64 | Microsoft Docs"
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
  - "_findfirst"
  - "_wfindfirst"
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
  - "findfirst32i64"
  - "wfindfirst32i64"
  - "tfindfirst64"
  - "_findfirst64i32"
  - "_wfindfirst32i64"
  - "_wfindfirsti64"
  - "wfindfirst"
  - "_tfindfirsti64"
  - "findfirst32"
  - "_tfindfirst32"
  - "_findfirsti64"
  - "findfirst"
  - "wfindfirst64"
  - "wfindfirst32"
  - "tfindfirst32"
  - "_wfindfirst64i32"
  - "findfirst64i32"
  - "tfindfirst64i32"
  - "_wfindfirst"
  - "findfirsti64"
  - "_findfirst32i64"
  - "wfindfirst64i32"
  - "_wfindfirst32"
  - "_findfirst32"
  - "_tfindfirst32i64"
  - "tfindfirst"
  - "_tfindfirst64i32"
  - "findfirst64"
  - "_tfindfirst"
  - "_findfirst64"
  - "_tfindfirst64"
  - "tfindfirst32i64"
  - "_findfirst"
  - "_wfindfirst64"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tfindfirst64 함수"
  - "_wfindfirst64i32 함수"
  - "_wfindfirst32i64 함수"
  - "wfindfirst32 함수"
  - "_findfirst 함수"
  - "wfindfirst64 함수"
  - "_wfindfirst 함수"
  - "_findfirst64i32 함수"
  - "wfindfirst 함수"
  - "_findfirst64 함수"
  - "tfindfirst32 함수"
  - "_tfindfirst64i32 함수"
  - "findfirst 함수"
  - "findfirst32i64 함수"
  - "tfindfirst64 함수"
  - "_tfindfirst32 함수"
  - "tfindfirst32i64 함수"
  - "tfindfirst64i32 함수"
  - "_wfindfirsti64 함수"
  - "_findfirst32i64 함수"
  - "findfirst32 함수"
  - "findfirsti64 함수"
  - "findfirst64i32 함수"
  - "tfindfirsti64 함수"
  - "tfindfirst 함수"
  - "_wfindfirst32 함수"
  - "wfindfirsti64 함수"
  - "_tfindfirsti64 함수"
  - "_tfindfirst 함수"
  - "_tfindfirst32i64 함수"
  - "findfirst64 함수"
  - "_findfirst32 함수"
  - "_findfirsti64 함수"
  - "wfindfirst32i64 함수"
  - "wfindfirst64i32 함수"
  - "_wfindfirst64 함수"
ms.assetid: 9bb46d1a-b946-47de-845a-a0b109a33ead
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`filespec` 인수에서 지정된 파일과 일치하는 파일이름의 첫 번째 인스턴스에 관한 정보를 제공합니다.  
  
## 구문  
  
```  
intptr_t _findfirst(  
   const char *filespec,  
   struct _finddata_t *fileinfo   
);  
intptr_t _findfirst32(  
   const char *filespec,  
   struct _finddata32_t *fileinfo   
);  
intptr_t _findfirst64(  
   const char *filespec,  
   struct _finddata64_t *fileinfo   
);  
intptr_t _findfirsti64(  
   const char *filespec,  
   struct _finddatai64_t *fileinfo   
);  
intptr_t _findfirst32i64(  
   const char *filespec,  
   struct _finddata32i64_t *fileinfo   
);  
intptr_t _findfirst64i32(  
   const char *filespec,  
   struct _finddata64i32_t *fileinfo   
);  
intptr_t _wfindfirst(  
   const wchar_t *filespec,  
   struct _wfinddata_t *fileinfo   
);  
intptr_t _wfindfirst32(  
   const wchar_t *filespec,  
   struct _wfinddata32_t *fileinfo   
);  
intptr_t _wfindfirst64(  
   const wchar_t *filespec,  
   struct _wfinddata64_t *fileinfo   
);  
intptr_t _wfindfirsti64(  
   const wchar_t *filespec,  
   struct _wfinddatai64_t *fileinfo   
);  
intptr_t _wfindfirst32i64(  
   const wchar_t *filespec,  
   struct _wfinddata32i64_t *fileinfo   
);  
intptr_t _wfindfirst64i32(  
   const wchar_t *filespec,  
   struct _wfinddata64i32_t *fileinfo   
);  
```  
  
#### 매개 변수  
 `filespec`  
 대상 파일 사양 \(와일드 카드 문자를 포함할 수 있습니다\).  
  
 `fileinfo`  
 파일 정보 버퍼.  
  
## 반환 값  
 만일 성공하면, `_findfirst` 는 `filespec` 사양에 일치하는 파일 또는 파일들의 그룹을 식별하는 고유한 검색 핸들을 반환하는데, 이것은 `_findclose` 또는 [\_findnext](../../c-runtime-library/reference/findnext-functions.md) 에 대한 후속 호출에 사용될 수 있습니다.  그렇지 않으면, `_findfirst` 는 \-1을 반환하고 다음 값들 중 하나를 `errno` 로 설정합니다.  
  
 `EINVAL`  
 잘못된 매개변수: `filespec` 또는 `fileinfo` 이 `NULL`입니다.  또는, 운영 체제는 예측하지 못한 오류를 반환합니다.  
  
 `ENOENT`  
 파일 사양에 일치하지 않습니다.  
  
 `ENOMEM`  
 메모리가 부족합니다.  
  
 `EINVAL`  
 잘못된 파일 이름 또는 파일 이름이 `MAX_PATH` 보다 큽니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 만일 잘못된 매개변수가 전달된 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 나타난 것처럼 이 함수는 잘못된 매개변수 처리기를 호출합니다.  
  
## 설명  
 `_findfirst` 또는 `_findnext` 함수\(또는 모든 변형들\) 중 하나가 끝난 후에 [\_findclose](../../c-runtime-library/reference/findclose.md) 를 호출 해야합니다.  이 것은 응용 프로그램에서 이러한 함수에 의해 사용 되는 리소스를 해제합니다.  
  
 이러한 함수들의 변형은 와이드 문자 버전들인 `w` 접두사를 갖습니다; 그렇지 않으면, 대응되는 싱글바이트 함수들로 식별됩니다.  
  
 이러한 함수의 변형 시간은 32 비트 또는 64 비트 형식과 32 비트 또는 64 비트 길이를 지원합니다.  첫 번째 숫자 접미사 \(`32` 또는 `64`\) 는 시간 형식의 크기를 나타내고 둘째 접미사는 파일 길이가 32비트 또는 64 비트 정수로 표시되는 지를 알려주는 `i32` 또는 `i64` 입니다.  32 비트 및 64 비트 형식 및 파일 크기를 지원하는 버전들에 대한 자세한 정보는, 다음 표를 참조하세요.  만일 시간 형식의 크기가 같다면, `i32` 또는 `i64` 접미사가 생략하여 `_findfirst64` 는 64비트 파일 길이 역시 지원하고, `_findfirst32` 는 오직 32비트 파일 길이만을 지원합니다.  
  
 이러한 함수를 는 `fileinfo` 매개변수에 대한 `_finddata_t` 구조체의 다양한 형식들을 사용합니다.  이 구조체에 대한 자세한 내용은 [파일 이름 검색 함수](../../c-runtime-library/filename-search-functions.md) 를 참조하세요.  
  
 64 비트 시간 형식을 사용하는 이 변형은 3000년, 12월 31일 23시 59분 59초 UTC, 까지의 파일 작성 날짜를 표현할 수 있습니다.  32 비트 시간 형식을 사용하는 경우, 2038년 1월 18일 19시 14분 07초 UTC, 까지의 날짜를 나타냅니다.  1970년 1월 1일 자정은 모든 함수의 날짜 범위의 하한 값입니다.  
  
 명시적으로 시간의 크기를 지정하는 버전을 사용할 특별한 이유가 없다면, `_findfirst` 또는 `_wfindfirst` 을 사용하거나, 만일 3GB보다 큰 파일 크기를 지원해야 할 경우 `_findfirsti64` 또는 `_wfindfirsti64` 를 사용합니다.  이러한 모든 함수는 64 비트 시간 형식을 사용합니다.  이전 버전에서는, 이러한 함수는 32비트 시간 형식을 사용했습니다.  만일 이것이 응용 프로그램에 대해 다른 부분에 문제를 일으키는 경우, 이전 동작으로 되돌리기 위해 `_USE_32BIT_TIME_T` 를 정의할 수 있습니다.  만일 `_USE_32BIT_TIME_T` 이 정의된 경우, `_findfirst` , `_finfirsti64` , 그리고 해당 유니코드 버전은 32비트 시간을 사용합니다.  
  
### \_findfirst의 시간 형식 및 파일 길이 형식 변형  
  
|함수|`_USE_32BIT_TIME_T`가 정의되었습니까?|시간 형식|파일 길이 형식입니다.|  
|--------|-----------------------------------|-----------|------------------|  
|`_findfirst`, `_wfindfirst`|정의 되지 않음|64비트|32비트|  
|`_findfirst`, `_wfindfirst`|정의됨|32비트|32비트|  
|`_findfirst32`, `_wfindfirst32`|매크로 정의에 영향을 받지 않음|32비트|32비트|  
|`_findfirst64`, `_wfindfirst64`|매크로 정의에 영향을 받지 않음|64비트|64비트|  
|`_findfirsti64`, `_wfindfirsti64`|정의 되지 않음|64비트|64비트|  
|`_findfirsti64`, `_wfindfirsti64`|정의됨|32비트|64비트|  
|`_findfirst32i64`, `_wfindfirst32i64`|매크로 정의에 영향을 받지 않음|32비트|64비트|  
|`_findfirst64i32`, `_wfindfirst64i32`|매크로 정의에 영향을 받지 않음|64비트|32비트|  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tfindfirst`|`_findfirst`|`_findfirst`|`_wfindfirst`|  
|`_tfindfirst32`|`_findfirst32`|`_findfirst32`|`_wfindfirst32`|  
|`_tfindfirst64`|`_findfirst64`|`_findfirst64`|`_wfindfirst64`|  
|`_tfindfirsti64`|`_findfirsti64`|`_findfirsti64`|`_wfindfirsti64`|  
|`_tfindfirst32i64`|`_findfirst32i64`|`_findfirst32i64`|`_wfindfirst32i64`|  
|`_tfindfirst64i32`|`_findfirst64i32`|`_findfirst64i32`|`_wfindfirst64i32`|  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_findfirst`|\<io.h\>|  
|`_findfirst32`|\<io.h\>|  
|`_findfirst64`|\<io.h\>|  
|`_findfirsti64`|\<io.h\>|  
|`_findfirst32i64`|\<io.h\>|  
|`_findfirst64i32`|\<io.h\>|  
|`_wfindfirst`|\<io.h\> or \<wchar.h\>|  
|`_wfindfirst32`|\<io.h\> or \<wchar.h\>|  
|`_wfindfirst64`|\<io.h\> or \<wchar.h\>|  
|`_wfindfirsti64`|\<io.h\> or \<wchar.h\>|  
|`_wfindfirst32i64`|\<io.h\> or \<wchar.h\>|  
|`_wfindfirst64i32`|\<io.h\> or \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::IO::Directory::GetFiles](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.getfiles.aspx)  
  
## 참고 항목  
 [시스템 호출](../../c-runtime-library/system-calls.md)   
 [파일 이름 검색 함수](../../c-runtime-library/filename-search-functions.md)