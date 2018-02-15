---
title: vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _vsnprintf
- _vsnprintf_l
- _vsnwprintf
- _vsnwprintf_l
- _vsnprintf
- _vsnprintf;
- vsnprintf; _vsnprintf
- _vsnwprintf;
- _vsnprintf_l;
- _vsnwprintf_l;
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _vsnprintf
- _vsnwprintf
- _vsntprintf
- vsnprintf
- stdio/vsnprintf
- stdio/_vsnprintf
- stdio/_vsnprintf_l
- stdio/_vsnwprintf
- stdio/_vsnwprintf_l
- _vsnprintf_l
- _vsnwprintf_l
dev_langs:
- C++
helpviewer_keywords:
- vsntprintf function
- _vsnwprintf_l function
- vsnwprintf_l function
- vsntprintf_l function
- _vsntprintf function
- _vsnprintf_l function
- vsnprintf function
- _vsntprintf_l function
- vsnprintf_l function
- _vsnwprintf function
- _vsnprintf function
- formatted text [C++]
- vsnwprintf function
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f5af34f038d9464b771bff4d982836c3b62d09db
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="vsnprintf-vsnprintf-vsnprintfl-vsnwprintf-vsnwprintfl"></a>vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l
인수 목록에 대한 포인터를 사용하여 형식이 지정된 출력을 씁니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](../../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int vsnprintf(  
   char *buffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf(  
   char *buffer,  
   size_t count,  
   const char *format,  
   va_list argptr   
);  
int _vsnprintf_l(  
   char *buffer,  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vsnwprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
);  
int _vsnwprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
template <size_t size>  
int vsnprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnprintf_l(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   va_list argptr   
); // C++ only  
template <size_t size>  
int _vsnwprintf_l(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `buffer`  
 출력을 위한 저장소 위치입니다.  
  
 `count`  
 작성할 최대 문자 수입니다.  
  
 `format`  
 형식 사양입니다.  
  
 `argptr`  
 인수 목록에 대한 포인터입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 [형식 사양](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하세요.  
  
## <a name="return-value"></a>반환 값  
 `vsnprintf` 함수는 종결 null 문자를 제외하고 작성된 문자 수를 반환합니다. `count`로 지정된 버퍼 크기가 `format` 및 `argptr`로 지정된 출력을 포함할 만큼 충분히 크지 않으면 `vsnprintf`의 반환 값은 `count`가 충분히 클 경우에 작성될 수 있는 문자 수입니다(null 문자는 계산에 포함되지 않음). 반환 값이 `count` -1보다 큰 경우 출력이 잘렸습니다. 반환 값 -1은 인코딩 오류가 발생했음을 나타냅니다.  
  
 작성할 문자 수가 `count`보다 작거나 같으면 `_vsnprintf` 및 `_vsnwprintf` 함수 둘 다 작성된 문자 수를 반환하고, 작성할 문자 수가 `count`보다 크면 출력이 잘렸음을 나타내는 -1을 반환합니다.  
  
 이러한 모든 함수에서 반환하는 값에는 작성 여부와 관계없이 종결 null이 포함되지 않습니다. `count`가 0이면 반환되는 값은 함수가 작성할 문자의 수이며 종결 null은 포함되지 않습니다. 이 결과를 사용하여 문자열과 해당 종결 null에 대해 충분한 버퍼 공간을 할당한 다음 함수를 다시 호출하여 버퍼를 채울 수 있습니다.  
  
 `format`이 `NULL`이거나 `buffer`가 NULL이고 `count`가 0과 같지 않으면 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 호출된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 이러한 함수가 -1을 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
## <a name="remarks"></a>설명  
 이러한 함수는 각각 인수 목록에 대한 포인터를 가져와서 데이터의 형식을 지정하고 `count` 가 가리키는 메모리에 `buffer`만큼의 문자를 작성합니다. `vsnprintf` 함수는 출력을 자르더라도 항상 null 종결자를 씁니다. `_vsnprintf` 및 `_vsnwprintf`를 사용하는 경우 끝에 공간이 있는 경우에만(즉, 작성할 문자 수가 `count`보다 작은 경우) 버퍼가 null로 종료됩니다.  
  
> [!IMPORTANT]
>  특정 종류의 보안 위험을 방지하려면 `format` 이 사용자 정의 문자열이 아닌지 확인하세요. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
> [!NOTE]
>  `_vsnprintf`, `_vsnprintf_l`, `_vsnwprintf` 및 `_vsnwprintf_l`를 호출할 때 종료 null에 대한 공간이 있게 하려면 `count` 가 버퍼 길이보다 작아야 하고 함수를 호출하기 전에 버퍼를 null로 초기화해야 합니다.  
>   
>  `vsnprintf`는 항상 종결 null을 작성하므로 `count` 매개 변수는 버퍼의 크기와 같을 수 있습니다.  
  
 Visual Studio 2015 및 Windows 10의 UCRT부터         `vsnprintf` 는 더 이상 `_vsnprintf`와 같지 않습니다. `vsnprintf` 함수는 C99 표준을 준수하며 `_vnsprintf`는 이전 버전 Visual Studio 코드와의 호환성을 위해 유지됩니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vsntprintf`|`_vsnprintf`|`_vsnprintf`|`_vsnwprintf`|  
|`_vsntprintf_l`|`_vsnprintf_l`|`_vsnprintf_l`|`_vsnwprintf_l`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|  
|-------------|---------------------------|-------------------------------|  
|`vsnprintf`, `_vsnprintf`, `_vsnprintf_l`|\<stdio.h>|\<stdio.h> 또는  \<cstdio>|  
|`_vsnwprintf`, `_vsnwprintf_l`|\<stdio.h> 또는 \<wchar.h>|\<stdio.h>, \<wchar.h>, \<cstdio> 또는 \<cwchar>|  
  
 `_vsnprintf`, `_vsnprintf_l`, `_vsnwprintf` 및 `_vsnwprintf_l` 함수는 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
  
```C  
// crt_vsnwprintf.c  
// compile by using: cl /W3 crt_vsnwprintf.c  
  
// To turn off error C4996, define this symbol:  
#define _CRT_SECURE_NO_WARNINGS  
  
#include <stdio.h>  
#include <wtypes.h>  
  
#define BUFFCOUNT (10)  
  
void FormatOutput(LPCWSTR formatstring, ...)  
{  
    int nSize = 0;  
    wchar_t buff[BUFFCOUNT];  
    memset(buff, 0, sizeof(buff));  
    va_list args;  
    va_start(args, formatstring);  
    // Note: _vsnwprintf is deprecated; consider vsnwprintf_s instead  
    nSize = _vsnwprintf(buff, BUFFCOUNT - 1, formatstring, args); // C4996  
    wprintf(L"nSize: %d, buff: %ls\n", nSize, buff);  
    va_end(args);
}  
  
int main() {  
    FormatOutput(L"%ls %ls", L"Hi", L"there");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!");  
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");  
}  
```  
  
```Output  
nSize: 8, buff: Hi there  
nSize: 9, buff: Hi there!  
nSize: -1, buff: Hi there!  
```  
  
 좁은 문자열 매개 변수와 함께 vsnprintf를 대신 사용하면 동작이 변경됩니다. `count` 매개 변수는 버퍼의 전체 크기일 수 있으며 반환 값은 `count`가 충분히 큰 경우 작성되었을 문자 수입니다.  
  
## <a name="example"></a>예  
  
```C  
// crt_vsnprintf.c  
// compile by using: cl /W4 crt_vsnprintf.c  
#include <stdio.h>  
#include <stdarg.h> // for va_list, va_start  
#include <string.h> // for memset  
  
#define BUFFCOUNT (10)  
  
void FormatOutput(char* formatstring, ...)  
{  
    int nSize = 0;  
    char buff[BUFFCOUNT];  
    memset(buff, 0, sizeof(buff));  
    va_list args;  
    va_start(args, formatstring);  
    nSize = vsnprintf(buff, sizeof(buff), formatstring, args);  
    printf("nSize: %d, buff: %s\n", nSize, buff);
    va_end(args);  
}  
  
int main() {  
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null  
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null  
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null  
}  
```  
  
```Output  
nSize: 8, buff: Hi there  
nSize: 9, buff: Hi there!  
nSize: 10, buff: Hi there!  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)   
 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)
