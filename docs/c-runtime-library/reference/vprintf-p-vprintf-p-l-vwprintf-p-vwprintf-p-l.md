---
title: "_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vwprintf_p"
  - "_vprintf_p"
  - "_vprintf_p_l"
  - "_vwprintf_p_l"
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
  - "_vwprintf_p_l"
  - "vprintf_p"
  - "_vprintf_p_l"
  - "_vwprintf_p"
  - "vprintf_p_l"
  - "vwprintf_p_l"
  - "vwprintf_p"
  - "vtprintf_p"
  - "_vtprintf_p"
  - "_vprintf_p"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vprintf_p 함수"
  - "_vprintf_p_l 함수"
  - "_vtprintf_p 함수"
  - "_vtprintf_p_l 함수"
  - "_vwprintf_p 함수"
  - "_vwprintf_p_l 함수"
  - "서식 있는 텍스트[C++]"
  - "vprintf_p 함수"
  - "vprintf_p_l 함수"
  - "vtprintf_p 함수"
  - "vtprintf_p_l 함수"
  - "vwprintf_p 함수"
  - "vwprintf_p_l 함수"
ms.assetid: 3f99bde3-c891-493d-908f-30559c421058
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인수 목록에 대한 포인터를 사용하여 형식이 지정 된 출력에 씁니다. 그리고 인수가 사용 되는 순서를 지정할 수 있습니다.  
  
## 구문  
  
```  
int _vprintf_p(  
   const char *format,  
   va_list argptr   
);  
int _vprintf_p_l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vwprintf_p(  
   const wchar_t *format,  
   va_list argptr   
);  
int _vwprintf_p_l(  
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
 `_vprintf_p` 와 `_vwprintf_p` 는 NULL 문자로 끝나거나 오류가 발생한 경우의 네이티브 값을 제외한 작성된 문자의 수를 반환합니다.  
  
## 설명  
 인수 목록에 대한 포인터 각각이 함수 다음 서식을 지정하고 지정 된 데이터를 쓰는 `stdout`입니다.  이러한 함수에서 다 `vprintf_s` 및 `vwprintf_s` 만 해당 인수 사용 되는 순서를 지정 하는 기능을 지원 합니다.  자세한 내용은 [printf\_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)을 참조하십시오.  
  
 `_vwprintf_p` 와이드 문자 버전인 `_vprintf_p` ;마치 동일한 스트림에서 ANSI 모드에서 열리는 경우입니다.  `_vprintf_p` 는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하십시오.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
 `format` 는 null포인터 입니다. 형식 문자열이 잘못된 형식의 문자를 포함하고 있을 경우, 잘못된 매개변수 처리기는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로, 호출됩니다.  계속해서 실행하도록 허용된 경우, 함수는 \-1을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_vtprintf_p`|`_vprintf_p`|`_vprintf_p`|`_vwprintf_p`|  
|`_vtprintf_p_l`|`_vprintf_p_l`|`_vprintf_p_l`|`_vwprintf_p_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_vprintf_p`, `_vprintf_p_l`|\<stdio.h\> 과 \<stdarg.h\>|\<varargs.h\>\*|  
|`_vwprintf_p`, `_vwprintf_p_l`|\<stdio.h\> 또는 \<wchar.h\>, 및 \<stdarg.h\>|\<varargs.h\>\*|  
  
 \*는 UNIX V 호환성을 위해 필요합니다.  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)   
 [vsprintf\_s, \_vsprintf\_s\_l, vswprintf\_s, \_vswprintf\_s\_l](../../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)   
 [\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)   
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf\_p 위치 매개 변수](../../c-runtime-library/printf-p-positional-parameters.md)