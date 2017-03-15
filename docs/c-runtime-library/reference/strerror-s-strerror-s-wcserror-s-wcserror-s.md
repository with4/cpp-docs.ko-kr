---
title: "strerror_s, _strerror_s, _wcserror_s, __wcserror_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__wcserror_s"
  - "_strerror_s"
  - "_wcserror_s"
  - "strerror_s"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wcserror_s"
  - "__wcserror_s"
  - "_tcserror_s"
  - "_wcserror_s"
  - "tcserror_s"
  - "strerror_s"
  - "_strerror_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wcserror_s 함수"
  - "_strerror_s 함수"
  - "_tcserror_s 함수"
  - "_wcserror_s 함수"
  - "오류 메시지, 가져오기"
  - "오류 메시지, 인쇄"
  - "오류 메시지 인쇄"
  - "strerror_s 함수"
  - "tcserror_s 함수"
  - "wcserror_s 함수"
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# strerror_s, _strerror_s, _wcserror_s, __wcserror_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

시스템 오류 메시지 \(`strerror_s`, `_wcserror_s`\) 를 가져오거나 사용자가 제공하는 오류 메시지\(`_strerror_s`, `__wcserror_s`\) 를 출력합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [strerror, \_strerror, \_wcserror, \_\_wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) 버전입니다.  
  
## 구문  
  
```  
errno_t strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t _strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   const char *strErrMsg   
);  
errno_t _wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t __wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *strErrMsg   
);  
template <size_t size>  
errno_t strerror_s(  
   char (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t _strerror_s(  
   char (&buffer)[size],  
   const char *strErrMsg   
); // C++ only  
template <size_t size>  
errno_t _wcserror_s(  
   wchar_t (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t __wcserror_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *strErrMsg   
); // C++ only  
```  
  
#### 매개 변수  
 `buffer`  
 오류 문자열을 저장할 버퍼입니다.  
  
 `numberOfElements`  
 버퍼의 크기입니다.  
  
 `errnum`  
 오류 번호.  
  
 `strErrMsg`  
 사용자가 제공하는 메시지입니다.  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
### 오류 조건  
  
|`buffer`|`numberOfElements`|`strErrMsg`|`buffer`의 내용입니다.|  
|--------------|------------------------|-----------------|----------------------|  
|`NULL`|any|any|해당 없음|  
|any|0|any|수정 안 됨|  
  
## 설명  
 `strerror_s` 함수는 `buffer` 에서 문자열을 반환하며 `errnum` 를 오류 메시지 문자열에 매핑합니다.  `_strerror_s` 는 오류번호를 가지지 않고 `errno` 의 현재 값을 사용하여 적절한 메시지를 결정합니다.   `strerror_s` 와 `_strerror_s` 는 실제로 메시지를 호출하지 않습니다. 따라서 [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) 와 같은 출력 함수를 호출해주어야 합니다.  
  
```  
if (( _access( "datafile",2 )) == -1 )  
{  
   _strerror_s(buffer, 80);  
   fprintf( stderr, buffer );  
}  
```  
  
 `strErrMsg` 가 `NULL` 인 경우, `_strerror_s` 는 오류를 발생시킨 마지막 라이브러리 호출에 대한 시스템 오류 메시지를 포함하는 문자열을 `buffer` 에서 반환합니다.  오류 메시지 문자열은 줄 바꿈 문자 \('\\n'\)에 의해 종료 됩니다.   `strErrMsg` 가 `NULL` 이 아닌 경우라면 `_strerror_s` 는 `buffer` 에서 \(유효한\)사용자의 문자열 메시지, 콜론, 공백, 오류를 발생시킨 마지막 라이브러리 호출에 대한 시스템 메시지와 줄바꿈 문자를 포함하는 문자열을 반환합니다.  사용자의 문자열 메시지는 최대 94자 까지 가능합니다.  
  
 이러한 함수는 오류 메시지의 길이가 `numberOfElements` \-1 을 초과하면 길이를 줄입니다.   `buffer` 에서 결과 문자열은 항상 null로 끝납니다.  
  
 `_strerror_s` 에 대한 실제 오류 번호는 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 에 저장됩니다.  시스템 에러 메시지는 [\_sys\_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수를 통해 액세스 되는데, 이것은 오류 번호에 따라 정렬된 메시지의 배열입니다.  `_strerror_s` 는 `errno` 값을 변수 `_sys_errlist` 에 대한 인덱스로 사용해 적절한 오류 메시지에 액세스할 수 있습니다.  변수 [\_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 의 값은 `_sys_errlist` 배열 내에서 요소의 최대 수로 정의됩니다.  정확한 결과를 생성하려면, 라이브러리 루틴이 오류와 함께 반환하는 즉시 `_strerror_s` 를 호출하십시오.  그렇지 않으면, `strerror_s` 또는 `_strerror_s` 에 대한 다음 호출이 `errno` 값을 덮어 쓸수도 있습니다.  
  
 `_wcserror_s` 와 `__wcserror_s`는 각각 `strerror_s`와 `_strerror_s` 의 와이드 문자 버전입니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다.  버퍼가 `NULL` 이거나 크기 매개 변수가 0인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된대로 잘못된 매개 변수 처리기가 호출됩니다.  실행을 계속할 수 있는 경우 함수는 `EINVAL` 을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
 `_strerror_s, _wcserror_s,` 와 `__wcserror_s` 는 ANSI 정의의 일부는 아니지만 대신에 Microsoft 확장입니다.  이식성이 필요한 곳에는 사용하지 마십시오; ANSI 호환성에 대해 대신 `strerror_s` 을 사용하십시오.  
  
 C\+\+에서는 이러한 함수를 사용하는 것은 템플릿 오버로드에 의해 단순화됩니다; 오버로드는 자동으로 버퍼의 길이를 추정할수 있고, 크기 인수를 지정할 필요를 없앱니다.  자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하십시오.  
  
 이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다.  이 동작을 사용하지 않으려면 [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)를 사용하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcserror_s`|`strerror_s`|`strerror_s`|`_wcserror_s`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`strerror_s`, `_strerror_s`|\<string.h\>|  
|`_wcserror_s`, `__wcserror_s`|\<string.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [perror](../../c-runtime-library/reference/perror-wperror.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Exception::Message](https://msdn.microsoft.com/en-us/library/system.exception.message.aspx)  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)