---
title: "vprintf, _vprintf_l, vwprintf, _vwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vprintf"
  - "_vwprintf_l"
  - "_vprintf_l"
  - "vwprintf"
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
apitype: "DLLExport"
f1_keywords: 
  - "vwprintf"
  - "_vtprintf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_vprintf_l 함수"
  - "_vtprintf 함수"
  - "_vtprintf_l 함수"
  - "_vwprintf_l 함수"
  - "서식 있는 텍스트[C++]"
  - "vprintf 함수"
  - "vprintf_l 함수"
  - "vtprintf 함수"
  - "vtprintf_l 함수"
  - "vwprintf 함수"
  - "vwprintf_l 함수"
ms.assetid: 44549505-00a0-4fa7-9a85-f2e666f55a38
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vprintf, _vprintf_l, vwprintf, _vwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인수 목록에 대한 포인터를 사용하여 서식이 지정된 출력을 작성합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [vprintf\_s, \_vprintf\_s\_l, vwprintf\_s, \_vwprintf\_s\_l](../../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)를 참조하십시오.  
  
## 구문  
  
```  
int vprintf(  
   const char *format,  
   va_list argptr   
);  
int _vprintf_l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int vwprintf(  
   const wchar_t *format,  
   va_list argptr   
);  
int _vwprintf_l(  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### 매개 변수  
 `format`  
 형식 사양입니다.  
  
 `argptr`  
 인수 목록에 대한 포인터입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하십시오.  
  
## 반환 값  
 `vprintf` 와 `vwprintf` 는 NULL 문자로 끝나거나 오류가 발생한 경우의 네이티브 값을 제외한 작성된 문자의 수를 반환합니다.  `format` 는 null포인터 입니다. 형식 문자열이 잘못된 형식의 문자를 포함하고 있을 경우, 잘못된 매개변수 처리기는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로, 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 \-1을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 인수 목록에 대한 포인터 각각이 함수 다음 서식을 지정하고 지정 된 데이터를 쓰는 `stdout`입니다.  
  
 `vwprintf` 는 와이드 문자 버전인 `vprintf` 입니다; 마치 동일한 스트림에서 ANSI 모드에서 열리는 경우입니다.  `vprintf` 는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하십시오.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  잘못된 형식 문자열 검색하고 오류가 발생 합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_vtprintf`|`vprintf`|`vprintf`|`vwprintf`|  
|`_vtprintf_l`|`_vprintf_l`|`_vprintf_l`|`_vwprintf_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`vprintf`, `_vprintf_l`|\<stdio.h\> 과 \<stdarg.h\>|\<varargs.h\>\*|  
|`vwprintf`, `_vwprintf_l`|\<stdio.h\> 또는 \<wchar.h\>, 및 \<stdarg.h\>|\<varargs.h\>\*|  
  
 \*는 UNIX V 호환성을 위해 필요합니다.  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)