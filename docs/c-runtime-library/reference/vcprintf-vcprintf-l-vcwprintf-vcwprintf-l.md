---
title: "_vcprintf, _vcprintf_l, _vcwprintf, _vcwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_vcwprintf"
  - "_vcprintf_l"
  - "_vcwprintf_l"
  - "_vcprintf"
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
  - "_vcwprintf_l"
  - "_vtcprintf"
  - "vcwprintf"
  - "_vcwprintf"
  - "vcprintf_l"
  - "_vcprintf_l"
  - "_vcprintf"
  - "vcprintf"
  - "vcwprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_vcprintf 함수"
  - "_vcprintf_l 함수"
  - "_vcwprintf 함수"
  - "_vcwprintf_l 함수"
  - "_vtcprintf 함수"
  - "_vtcprintf_l 함수"
  - "서식 있는 텍스트[C++]"
  - "vcprintf 함수"
  - "vcprintf_l 함수"
  - "vcwprintf 함수"
  - "vcwprintf_l 함수"
  - "vtcprintf 함수"
  - "vtcprintf_l 함수"
ms.assetid: 4ef8d237-6200-4b66-8731-8c57e5624bb1
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# _vcprintf, _vcprintf_l, _vcwprintf, _vcwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

쓰기는 인수 목록에 대한 포인터를 사용하여 콘솔에 출력을 포맷 합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_vcprintf\_s, \_vcprintf\_s\_l, \_vcwprintf\_s, \_vcwprintf\_s\_l](../../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _vcprintf(  
   const char* format,  
   va_list argptr  
);  
int _vcprintf_l(  
   const char* format,  
   locale_t locale,  
   va_list argptr  
);  
int _vcwprintf(  
   const wchar_t* format,  
   va_list argptr  
);  
int _vcwprintf_l(  
   const wchar_t* format,  
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
 인쇄된 문자 수를 반환하거나 오류가 발생하면 음수 값을 반환합니다.  `format` 이 null 포인터인 경우, 설명된 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, `errno` 는 `EINVAL` 와 \-1을 반환합니다.  
  
## 설명  
 이러한 함수의 각각은 인수 목록에 대한 포인터를 가지며, 서식을 지정하고 지정된 데이터를 가르키는 메모리에 작성됩니다.  `_vcwprintf` 는 `_vcprintf` 의 와이드 문자 버전입니다.  와이드 문자 문자열을 인수로 걸립니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하십시오.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_vtcprintf`|`_vcprintf`|`_vcprintf`|`_vcwprintf`|  
|`_vtcprintf_l`|`_vcprintf_l`|`_vcprintf_l`|`_vcwprintf_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_vcprintf`, `_vcprintf_l`|\<conio.h\> 및 \<stdarg.h\>|\<varargs.h\>\*|  
|`_vcwprintf`, `_vcwprintf_l`|\<stdio.h\> 또는 \<wchar.h\>, 및 \<stdarg.h\>|\<varargs.h\>\*|  
  
 \*는 UNIX V 호환성을 위해 필요합니다.  
  
 추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_vcprintf.cpp  
// compile with: /c  
#include <conio.h>  
#include <stdarg.h>  
  
// An error formatting function used to print to the console.  
int eprintf(const char* format, ...)  
{  
  va_list args;  
  va_start(args, format);  
  return _vcprintf(format, args);  
}  
  
int main()  
{  
   eprintf("  (%d:%d): Error %s%d : %s\n", 10, 23, "C", 2111,  
           "<some error text>");  
   eprintf("  (Related to symbol '%s' defined on line %d).\n",  
           "<symbol>", 5 );  
}  
```  
  
  **\(10,23\): 오류 C2111: \<오류 텍스트\>**  
 **\(기호 관련 '\<기호\>' 5 줄에 정의\).**   
## 해당 .NET Framework 항목  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va\_arg, va\_copy, va\_end, va\_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)