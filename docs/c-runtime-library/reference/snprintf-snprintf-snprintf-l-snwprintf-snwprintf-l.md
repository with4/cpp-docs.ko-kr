---
title: "snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l | Microsoft Docs"
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
  - "_snwprintf"
  - "_snprintf"
  - "_snprintf_l"
  - "_snwprintf_l"
  - "snprintf"
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
  - "_snprintf"
  - "snprintf_l"
  - "snwprintf_l"
  - "sntprintf"
  - "snprintf"
  - "_sntprintf"
  - "_sntprintf_l"
  - "sntprintf_l"
  - "snwprintf"
  - "_snprintf_l"
  - "_snwprintf"
  - "_snwprintf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "snwprintf_l 함수"
  - "sntprintf_l 함수"
  - "snprintf_l 함수"
  - "_snwprintf_l 함수"
  - "_sntprintf_l 함수"
  - "_snwprintf 함수"
  - "_snprintf 함수"
  - "_sntprintf 함수"
  - "_snprintf_l 함수"
  - "snwprintf 함수"
  - "snprintf 함수"
  - "sntprintf 함수"
  - "서식 있는 텍스트[C++]"
ms.assetid: 5976c9c8-876e-4ac9-a515-39f3f7fd0925
caps.latest.revision: 35
caps.handback.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열에 서식이 지정된 데이터를 씁니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)를 참조하세요.  
  
## 구문  
  
```  
int snprintf(  
   char *buffer,  
   size_t count,  
   const char *format [,  
   argument] ...   
);  
int _snprintf(  
   char *buffer,  
   size_t count,  
   const char *format [,  
   argument] ...   
);  
int _snprintf_l(  
   char *buffer,  
   size_t count,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _snwprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
);  
int _snwprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int _snprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snprintf_l(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snwprintf(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snwprintf_l(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
```  
  
#### 매개 변수  
 `buffer`  
 출력을 위한 저장소 위치입니다.  
  
 `count`  
 저장할 최대 문자 수입니다.  
  
 `format`  
 형식 컨트롤 문자열입니다.  
  
 `argument`  
 선택적 인수입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
 자세한 내용은 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)을 참조하십시오.  
  
## 반환 값  
 `len`은 종료 null을 포함하지 않는 데이터 형식이 지정된 문자열의 길이입니다.`len` 및 `count`는 `snprintf`의 경우 바이트이고, `_snprintf`의 경우 `_snwprintf`에 대한 와이드 문자입니다.  
  
 모든 함수에 대해 `len` \< `count`, `len` 문자가 `buffer`에 저장되는 경우 null 종결자가 추가되고 `len`이 반환됩니다.  
  
 `snprintf` 함수는 `len`이 `count`보다 크거나 같을 때 `buffer[count-1]`에 null 종결자를 배치하여 출력을 자릅니다. 반환 값은 `count`가 충분히 큰 경우 출력될 수 있는 문자 수인 `len`입니다.`snprintf` 함수는 인코딩 오류가 발생하는 경우 음수 값을 반환합니다.  
  
 `snprintf` 이외의 모든 함수에서 `len` \= `count`, `len` 문자가 `buffer`에 저장되는 경우 null 종결자가 추가되지 않고 `len`이 반환됩니다.`len` \> `count`, `count` 문자가 `buffer`에 저장되는 경우 null 종결자가 추가되지 않고 음수 값이 반환됩니다.  
  
 `buffer`가 null 포인터이고 `count`가 0인 경우 종료 null을 포함하지 않고 출력 형식을 지정하는 데 필요한 문자의 개수로 `len`이 반환됩니다. 동일한 `argument` 및 `locale` 매개 변수를 사용하여 성공적으로 호출하려면 최소한 `len` \+ 1자로 보유되는 버퍼를 할당합니다.  
  
 `buffer`가 null 포인터이고 `count`가 0이 아닌 경우 또는 `format`이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이러한 함수가 \-1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## 설명  
 `snprintf` 함수 및 `_snprintf` 함수 제품군은 `buffer`에 `count`자 미만의 형식을 지정하고 저장합니다.`snprintf` 함수는 항상 종료 null 문자를 저장하고, 필요한 경우 출력을 잘라냅니다.`_snprintf` 함수 제품군은 형식이 지정된 문자열 길이가 `count`자보다 작은 경우에만 종료 null 문자를 추가합니다. 각 `argument`\(있는 경우\)가 `format`의 해당 형식 사양에 따라 변환되어 출력됩니다. 형식은 일반 문자로 구성되어 있으며, [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)를 위한 `format` 인수와 동일한 형태와 기능을 가지고 있습니다. 중복되는 문자열 간에 복사가 이뤄지면 이 동작은 정의되지 않습니다.  
  
> [!IMPORTANT]
>  `format`이 사용자 정의 문자열이 아닌지 확인하세요.`_snprintf` 함수는 NULL 종료를 보장하지 않으므로, 특히 반환 값이 `count`이면 해당 값 뒤에 null 종결자를 추가하는 코드가 오는지 확인합니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요.  
  
 Visual Studio 2015 및 Windows 10의 UCRT부터 `snprintf`는 더 이상 `_snprintf`와 같지 않습니다.`snprintf` 함수 동작은 이제 C99 표준을 준수합니다.  
  
 `_snwprintf`는 `_snprintf`의 와이드 문자 버전이며, `_snwprintf`에 대한 포인터 인수는 와이드 문자 문자열입니다.`_snwprintf`에서 인코딩 오류의 탐지 방식은 `_snprintf`에서와 다를 수 있습니다.`_snwprintf`와 같이 `swprintf`가 `FILE` 유형의 대상 대신 문자열에 출력을 기록합니다.  
  
 `_l` 접미사가 있는 이러한 함수 버전은 현재 스레드 로캘 대신 전달된 로캘 매개 변수를 사용하는 경우를 제외하고는 동일합니다.  
  
 C\+\+에서 이러한 함수는 보다 최신의 안전한 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_sntprintf`|`_snprintf`|`_snprintf`|`_snwprintf`|  
|`_sntprintf_l`|`_snprintf_l`|`_snprintf_l`|`_snwprintf_l`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`snprintf`, `_snprintf`,  `_snprintf_l`|\<stdio.h\>|  
|`_snwprintf`, `_snwprintf_l`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```c  
// crt_snprintf.c  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
#if !defined(__cplusplus)  
typedef int bool;  
const bool true = 1;  
const bool false = 0;  
#endif  
  
#define FAIL 0 // change to 1 and see what happens  
  
int main(void)  
{  
   char buffer[200];  
   const static char s[] = "computer"  
#if FAIL  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
#endif  
   ;  
   const char c = 'l';   
   const int i = 35;  
#if FAIL  
   const double fp = 1e300; // doesn't fit in the buffer  
#else  
   const double fp = 1.7320534;  
#endif  
   /* !subtract one to prevent "squeezing out" the terminal nul! */  
   const int bufferSize = sizeof(buffer)/sizeof(buffer[0]) - 1;  
   int bufferUsed = 0;  
   int bufferLeft = bufferSize - bufferUsed;  
   bool bSuccess = true;  
   buffer[0] = 0;  
  
   /* Format and print various data: */  
  
   if (bufferLeft > 0)  
   {  
      int perElementBufferUsed = _snprintf(&buffer[bufferUsed],   
      bufferLeft, "   String: %s\n", s ); // C4996  
      // Note: _snprintf is deprecated; consider _snprintf_s instead  
      if (bSuccess = (perElementBufferUsed >= 0))  
      {  
         bufferUsed += perElementBufferUsed;  
         bufferLeft -= perElementBufferUsed;  
         if (bufferLeft > 0)  
         {  
            int perElementBufferUsed = _snprintf(&buffer[bufferUsed],   
            bufferLeft, "   Character: %c\n", c ); // C4996  
            if (bSuccess = (perElementBufferUsed >= 0))  
            {  
               bufferUsed += perElementBufferUsed;  
               bufferLeft -= perElementBufferUsed;  
               if (bufferLeft > 0)  
               {  
                  int perElementBufferUsed = _snprintf(&buffer  
                  [bufferUsed], bufferLeft, "   Integer: %d\n", i ); // C4996  
                  if (bSuccess = (perElementBufferUsed >= 0))  
                  {  
                     bufferUsed += perElementBufferUsed;  
                     bufferLeft -= perElementBufferUsed;  
                     if (bufferLeft > 0)  
                     {  
                        int perElementBufferUsed = _snprintf(&buffer  
                        [bufferUsed], bufferLeft, "   Real: %f\n", fp ); // C4996  
                        if (bSuccess = (perElementBufferUsed >= 0))  
                        {  
                           bufferUsed += perElementBufferUsed;  
                        }  
                     }  
                  }  
               }  
            }  
         }  
      }  
   }  
  
   if (!bSuccess)  
   {  
      printf("%s\n", "failure");  
   }  
   else  
   {  
      /* !store nul because _snprintf doesn't necessarily (if the string   
       * fits without the terminal nul, but not with it)!  
       * bufferUsed might be as large as bufferSize, which normally is   
       * like going one element beyond a buffer, but in this case   
       * subtracted one from bufferSize, so we're ok.  
       */  
      buffer[bufferUsed] = 0;  
      printf( "Output:\n%s\ncharacter count = %d\n", buffer, bufferUsed );  
   }  
   return EXIT_SUCCESS;  
}  
```  
  
```Output  
Output: String: computer Character: l Integer: 35 Real: 1.732053 character count = 69  
```  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf 함수](../../c-runtime-library/vprintf-functions.md)