---
title: "_findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wfindnext"
  - "_findnext"
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
  - "findnext"
  - "_wfindnext32i64"
  - "_tfindnext64i32"
  - "findnext32"
  - "findnext32i64"
  - "wfindnext64i32"
  - "_wfindnext"
  - "tfindnext64"
  - "findnexti64"
  - "_findnexti64"
  - "_tfindnexti64"
  - "_findnext64i32"
  - "tfindnexti64"
  - "tfindnext32"
  - "_wfindnext64i32"
  - "findnext64i32"
  - "_findnext"
  - "_tfindnext32i64"
  - "_wfindnext64"
  - "wfindnext"
  - "wfindnext32"
  - "tfindnext32i64"
  - "_findnext64"
  - "_tfindnext64"
  - "_wfindnext32"
  - "findnext64"
  - "_findnext32i64"
  - "tfindnext"
  - "wfindnexti64"
  - "tfindnext64i32"
  - "_tfindnext32"
  - "wfindnext32i64"
  - "wfindnext64"
  - "_wfindnexti64"
  - "_tfindnext"
  - "_findnext32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_wfindnexti64 함수"
  - "_tfindnext32 함수"
  - "wfindnexti64 함수"
  - "_wfindnext32i64 함수"
  - "findnext32i64 함수"
  - "tfindnext64i32 함수"
  - "_tfindnext64i32 함수"
  - "_findnext 함수"
  - "findnext64i32 함수"
  - "_tfindnext 함수"
  - "findnext32 함수"
  - "tfindnext32 함수"
  - "_findnext32 함수"
  - "_tfindnext32i64 함수"
  - "_wfindnext 함수"
  - "tfindnext 함수"
  - "_findnext64 함수"
  - "findnext64 함수"
  - "_findnext64i32 함수"
  - "wfindnext32i64 함수"
  - "findnext 함수"
  - "wfindnext32 함수"
  - "_wfindnext64i32 함수"
  - "findnexti64 함수"
  - "_wfindnext64 함수"
  - "_findnext32i64 함수"
  - "_findnexti64 함수"
  - "_tfindnext64 함수"
  - "wfindnext64i32 함수"
  - "tfindnexti64 함수"
  - "wfindnext64 함수"
  - "wfindnext 함수"
  - "tfindnext64 함수"
  - "_wfindnext32 함수"
  - "tfindnext32i64 함수"
  - "_tfindnexti64 함수"
ms.assetid: 75d97188-5add-4698-a46c-4c492378f0f8
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이전 [\_findfirst](../../c-runtime-library/reference/findfirst-functions.md) 호출에서 `filespec` 인수와 일치하는 다음 이름을 찾고 `fileinfo` 구조체 내용을 적절하게 변경합니다.  
  
## 구문  
  
```  
int _findnext(  
   intptr_t handle,  
   struct _finddata_t *fileinfo   
);  
int _findnext32(  
   intptr_t handle,  
   struct _finddata32_t *fileinfo   
);  
int _findnext64(  
   intptr_t handle,  
   struct __finddata64_t *fileinfo   
);  
int _findnexti64(  
   intptr_t handle,  
   struct __finddatai64_t *fileinfo   
);  
int _findnext32i64(  
   intptr_t handle,  
   struct _finddata32i64_t *fileinfo   
);  
int _findnext64i32(  
   intptr_t handle,  
   struct _finddata64i32_t *fileinfo   
);  
int _wfindnext(  
   intptr_t handle,  
   struct _wfinddata_t *fileinfo   
);  
int _wfindnext32(  
   intptr_t handle,  
   struct _wfinddata32_t *fileinfo   
);  
int _wfindnext64(  
   intptr_t handle,  
   struct _wfinddata64_t *fileinfo   
);  
int _wfindnexti64(  
   intptr_t handle,  
   struct _wfinddatai64_t *fileinfo   
);  
int _wfindnext32i64(  
   intptr_t handle,  
   struct _wfinddatai64_t *fileinfo   
);  
int _wfindnext64i32(  
   intptr_t handle,  
   struct _wfinddata64i32_t *fileinfo   
);  
```  
  
#### 매개 변수  
 `handle`  
 이전 호출에 의해 `_findfirst`로 반환된 처리기를 검색합니다.  
  
 `fileinfo`  
 파일 정보 버퍼.  
  
## 반환 값  
 성공하면 0를 반환합니다.  그렇지 않으면\-1을 반환하고 `errno`를 장애의 특성을 나타내는 값으로 설정합니다.  가능한 오류 코드는 다음 표와 같습니다.  
  
 `EINVAL`  
 잘못된 매개 변수입니다. `fileinfo`가 `NULL`입니다.  또는, 운영 체제는 예측하지 못한 오류를 반환합니다.  
  
 `ENOENT`  
 더 이상 일치하는 파일을 찾을 수 없습니다.  
  
 `ENOMEM`  
 메모리가 부족 하거나 파일 이름의 길이가 `MAX_PATH`를 초과했습니다.  
  
 만일 잘못된 매개변수가 전달된 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 나타난 것처럼 이 함수는 잘못된 매개변수 처리기를 호출합니다.  
  
## 설명  
 `_findfirst` 또는 `_findnext` 함수\(또는 모든 변형들\) 중 하나가 끝난 후에 [\_findclose](../../c-runtime-library/reference/findclose.md) 를 호출 해야합니다.  이 것은 응용 프로그램에서 이러한 함수에 의해 사용 되는 리소스를 해제합니다.  
  
 이러한 함수들의 변형은 와이드 문자 버전들인 `w` 접두사를 갖습니다; 그렇지 않으면, 대응되는 싱글바이트 함수들로 식별됩니다.  
  
 이러한 함수의 변형 시간은 32 비트 또는 64 비트 형식과 32 비트 또는 64 비트 길이를 지원합니다.  첫 번째 숫자 접미사 \(`32` 또는 `64`\) 는 사용 시간 형식의 크기를 나타내고 둘째 접미사는 파일 길이가 32비트 또는 64 비트 정수로 표시되는 지를 알려주는 `i32` 또는 `i64` 입니다.  32 비트 및 64 비트 형식 및 파일 크기를 지원하는 버전들에 대한 자세한 정보는, 다음 표를 참조하세요.  64비트 시간 형식을 사용하는 변종은 파일 생성 날짜를 23:59:59, 12월 31일, 3000, UTC까지 표현할 수 있습니다. 반면 32비트 시간 형식의 경우는 19:14:07 1월 18일, 2038, UTC까지만 가능합니다.  1970년 1월 1일 자정은 모든 함수의 날짜 범위의 하한 값입니다.  
  
 명시적으로 시간의 크기를 지정하는 버전을 사용할 특별한 이유가 없다면, `_findnext` 또는 `_wfindnext` 을 사용하거나, 만일 3GB보다 큰 파일 크기를 지원해야 할 경우 `_findnexti64` 또는 `_wfindnexti64` 를 사용합니다.  이러한 모든 함수는 64 비트 시간 형식을 사용합니다.  이전 버전에는 이러한 함수는 32비트 시간 형식을 사용합니다.  만일 이것이 응용 프로그램에 대해 다른 부분에 문제를 일으키는 경우, 이전 동작을 얻기 위해 `_USE_32BIT_TIME_T`를 정의할 수 있습니다.  만일 `_USE_32BIT_TIME_T` 이 정의된 경우, `_findnext` , `_finnexti64` , 그리고 해당 유니코드 버전은 32비트 시간을 사용합니다.  
  
### \_findnext의 시간 형식 및 파일 길이 형식 변형  
  
|함수|`_USE_32BIT_TIME_T`가 정의되었습니까?|시간 형식|파일 길이 형식입니다.|  
|--------|-----------------------------------|-----------|------------------|  
|`_findnext`, `_wfindnext`|정의 되지 않음|64비트|32비트|  
|`_findnext`, `_wfindnext`|정의됨|32비트|32비트|  
|`_findnext32`, `_wfindnext32`|매크로 정의에 영향을 받지 않음|32비트|32비트|  
|`_findnext64`, `_wfindnext64`|매크로 정의에 영향을 받지 않음|64비트|64비트|  
|`_findnexti64`, `_wfindnexti64`|정의 되지 않음|64비트|64비트|  
|`_findnexti64`, `_wfindnexti64`|정의됨|32비트|64비트|  
|`_findnext32i64`, `_wfindnext32i64`|매크로 정의에 영향을 받지 않음|32비트|64비트|  
|`_findnext64i32`, `_wfindnext64i32`|매크로 정의에 영향을 받지 않음|64비트|32비트|  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tfindnext`|`_findnext`|`_findnext`|`_wfindnext`|  
|`_tfindnext32`|`_findnext32`|`_findnext32`|`_wfindnext32`|  
|`_tfindnext64`|`_findnext64`|`_findnext64`|`_wfindnext64`|  
|`_tfindnexti64`|`_findnexti64`|`_findnexti64`|`_wfindnexti64`|  
|`_tfindnext32i64`|`_findnext32i64`|`_findnext32i64`|`_wfindnext32i64`|  
|`_tfindnext64i32`|`_findnext64i32`|`_findnext64i32`|`_wfindnext64i32`|  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_findnext`|\<io.h\>|  
|`_findnext32`|\<io.h\>|  
|`_findnext64`|\<io.h\>|  
|`_findnexti64`|\<io.h\>|  
|`_findnext32i64`|\<io.h\>|  
|`_findnext64i32`|\<io.h\>|  
|`_wfindnext`|\<io.h\> or \<wchar.h\>|  
|`_wfindnext32`|\<io.h\> or \<wchar.h\>|  
|`_wfindnext64`|\<io.h\> or \<wchar.h\>|  
|`_wfindnexti64`|\<io.h\> or \<wchar.h\>|  
|`_wfindnext32i64`|\<io.h\> or \<wchar.h\>|  
|`_wfindnext64i32`|\<io.h\> or \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [시스템 호출](../../c-runtime-library/system-calls.md)   
 [파일 이름 검색 함수](../../c-runtime-library/filename-search-functions.md)