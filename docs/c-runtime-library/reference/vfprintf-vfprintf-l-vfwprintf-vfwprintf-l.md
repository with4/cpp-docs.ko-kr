---
title: "vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vfprintf_l"
  - "vfprintf"
  - "vfwprintf"
  - "_vfwprintf_l"
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
  - "vfwprintf"
  - "_vftprintf"
  - "vfprintf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vfwprintf_l 함수"
  - "_vftprintf 함수"
  - "vfprintf 함수"
  - "_vftprintf_l 함수"
  - "vfprintf_l 함수"
  - "vftprintf_l 함수"
  - "vfwprintf_l 함수"
  - "vftprintf 함수"
  - "vfwprintf 함수"
  - "_vfprintf_l 함수"
  - "서식 있는 텍스트[C++]"
ms.assetid: 4443be50-cedf-40b2-b3e2-ff2b3af3b666
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인수 목록에 대한 포인터를 사용하여 형식이 지정된 출력을 씁니다. 이러한 함수의 더 안전한 버전 존재 합니다. 참조 [vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int vfprintf(  
   FILE *stream,  
   const char *format,  
   va_list argptr   
);  
int _vfprintf_l(  
   FILE *stream,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int vfwprintf(  
   FILE *stream,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vfwprintf_l(  
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
 `format`  
 형식 사양입니다.  
  
 `argptr`  
 인수 목록에 대한 포인터입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 참조 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 `vfprintf` 및 `vfwprintf`는 null 종결 문자를 포함하지 않고 작성된 문자 수를 반환하거나, 출력 오류가 발생하는 경우 음수 값을 반환합니다. 어느 경우 `stream` 또는 `format` 가 null 포인터에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 계속해서 실행하도록 허용한 경우 이러한 함수가 -1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 코드 및 기타 오류 코드에 대 한 자세한 내용은 참조 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다.  
  
## <a name="remarks"></a>주의  
 이러한 각 함수는 인수 목록에 대 한 포인터 다음 기록 하 고 형식을 지정 된 데이터를 `stream`합니다.  
  
 `vfwprintf` 와이드 문자 버전인 `vfprintf`; 스트림이 ANSI 모드에서 열리는 경우 두 함수는 동일 하 게 작동 합니다. `vfprintf`는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하세요. 자세한 내용은 참조 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vftprintf`|`vfprintf`|`vfprintf`|`vfwprintf`|  
|`_vftprintf_l`|`_vfprintf_l`|`_vfprintf_l`|`_vfwprintf_l`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|----------------------|  
|`vfprintf`, _`vfprintf_l`|\<stdio.h> 및 \<stdarg.h>|\<varargs.h>*|  
|`vfwprintf`, _`vfwprintf_l`|\<stdio.h> 또는 \<wchar.h> 및 \<stdarg.h>|\<varargs.h>*|  
  
 \* UNIX V 호환성을 위해 필요 합니다.  
  
 자세한 호환성 정보를 참조 하십시오. [호환성](../../c-runtime-library/compatibility.md) 에서 소개 합니다.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 적용할 수 없음 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 참조 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)