---
title: "setlocale, _wsetlocale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wsetlocale"
  - "setlocale"
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
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wsetlocale"
  - "_tsetlocale"
  - "setlocale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tsetlocale 함수"
  - "_wsetlocale 함수"
  - "로캘 정의"
  - "로캘, 정의"
  - "setlocale 함수"
  - "tsetlocale 함수"
  - "wsetlocale 함수"
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# setlocale, _wsetlocale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

런타임 로캘을 설정하거나 가져옵니다.  
  
## 구문  
  
```  
char *setlocale(  
   int category,  
   const char *locale   
);  
wchar_t *_wsetlocale(  
   int category,  
   const wchar_t *locale   
);  
```  
  
#### 매개 변수  
 `category`  
 로캘의 영향을 받는 범주입니다.  
  
 `locale`  
 로캘 지정자입니다.  
  
## 반환 값  
 유효한 `locale` 및 `category`가 지정된 경우 지정된 `locale` 및 `category`와 연결된 문자열에 대한 포인터를 반환합니다.  `locale` 또는 `category`가 유효하지 않을 경우 null 포인터를 반환하고 프로그램의 현재 로캘 설정은 변경되지 않습니다.  
  
 예: 호출  
  
 `setlocale( LC_ALL, "en-US" );`  
  
 문자열만 반환하는 모든 범주를 설정합니다.  
  
 `en-US`  
  
 프로그램 로캘 정보의 일부를 복원할 수 있도록 `setlocale`에서 반환된 문자열을 복사할 수 있습니다.  전역 또는 스레드 로컬 저장소는 `setlocale`에서 반환된 문자열에 사용됩니다.  `setlocale`에 대한 이후 호출이 문자열을 덮어쓰므로, 이전 호출에서 반환된 문자열 포인터가 무효화됩니다.  
  
## 설명  
 `setlocale` 함수를 사용하여 `locale` 및 `category`에 의해 지정된 현재 프로그램 로캘 정보의 일부 또는 전체를 설정, 변경 또는 쿼리합니다.  `locale`은 프로그램의 특정 측면을 사용자 지정할 수 있는 집약성\(국가\/지역 및 언어\)을 나타냅니다.  일부 로캘 종속 범주에는 날짜 형식 지정 및 통화 값의 형식 표시가 포함됩니다.  `locale`을 컴퓨터에서 지원되는 폼이 여러 개 있는 언어의 기본 문자열로 설정하는 경우 `setlocale` 반환 코드를 검사하여 적용되는 언어를 확인해야 합니다.  예를 들어, `locale`을 "중국어"로 설정하면 반환 값이 "중국어 간체" 또는 "중국어 번체"일 수 있습니다.  
  
 `_wsetlocale`은 `setlocale`의 와이드 문자 버전이고, `locale` 인수와 `_wsetlocale`의 반환 값은 와이드 문자 문자열입니다.  그렇지 않으면 `_wsetlocale`과 `setlocale`이 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tsetlocale`|`setlocale`|`setlocale`|`_wsetlocale`|  
  
 `category` 인수는 영향을 받는 프로그램 로캘 정보의 일부를 지정합니다.  `category`에 사용되는 매크로 및 영향을 받는 프로그램의 일부는 다음과 같습니다.  
  
 `LC_ALL`  
 다음 목록에 모든 범주가 나열됩니다.  
  
 `LC_COLLATE`  
 `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll` 및 `wcsxfrm` 함수입니다.  
  
 `LC_CTYPE`  
 문자 처리 함수\(영향을 받지 않는 `isdigit`, `isxdigit`, `mbstowcs` 및 `mbtowc` 제외\)입니다.  
  
 `LC_MONETARY`  
 `localeconv` 함수에 의해 반환되는 통화 서식 정보입니다.  
  
 `LC_NUMERIC`  
 서식이 지정된 출력 루틴\(예: `printf`\), 데이터 변환 루틴 및 `localeconv`에 의해 반환된 비통화 서식 정보에 대한 소수점 문자입니다.  소수점 문자 이외에도 `LC_NUMERIC`은 1000단위 구분 기호와 [localeconv](../../c-runtime-library/reference/localeconv.md)에 의해 반환된 그룹화 제어 문자열을 설정합니다.  
  
 `LC_TIME`  
 `strftime` 및 `wcsftime` 함수입니다.  
  
 이 함수는 범주 매개 변수의 유효성을 검사합니다.  범주 매개 변수가 이전 테이블에 지정된 값 중 하나가 아닌 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우 함수가`errno`를 `EINVAL`로 설정하고 `NULL`을 반환합니다.  
  
 `locale` 인수는 로캘을 지정하는 문자열에 대한 포인터입니다.  `locale` 인수의 형식에 대한 자세한 정보는 [로캘 이름, 언어 및 국가\/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)을 참조하십시오.  `locale`이 빈 문자열 가리키면 로캘은 구현 시 정의된 네이티브 환경입니다.  `C`의 값은 C 번역에 대한 최소 ANSI 표준에 맞는 환경을 지정합니다.  `C`로캘은 `char` 데이터 형식이 1바이트이고 해당 값이 항상 256보다 작은 것으로 가정합니다.  
  
 프로그램을 시작할 때 다음 문을 실행합니다.  
  
 `setlocale( LC_ALL, "C" );`  
  
 `locale` 인수는 로캘 이름, 언어 문자열, 언어 문자열 및 국가\/지역 코드, 코드 페이지, 언어 문자열, 국가\/지역 코드 및 코드 페이지를 가져올 수 있습니다.  사용 가능한 로캘 이름, 언어, 국가\/지역 코드 및 코드 페이지의 집합에는 문자당 2바이트 이상을 필요로 하는 코드 페이지를 제외하고, Windows NLS API에서 지원하는 모든 항목이 포함됩니다\(예: UTF\-7 및 UTF\-8\).  UTF\-7 또는 UTF\-8의 코드 페이지 값을 제공하는 경우 `setlocale`이 실패하고 NULL이 반환됩니다.  `setlocale`에 의해 지원되는 로캘 이름의 집합은 [로캘 이름, 언어 및 국가\/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)에 설명되어 있습니다.  `setlocale`에 의해 지원되는 언어 및 국가\/지역 문자열의 집합은 [언어 문자열](../../c-runtime-library/language-strings.md) 및 [국가\/지역 문자열](../../c-runtime-library/country-region-strings.md)에 나열되어 있습니다.  코드에 포함되거나 저장소에 직렬화된 로캘 문자열의 성능과 유지 관리를 위해 로캘 이름 형식을 사용하는 것이 좋습니다.  로캘 이름 문자열은 언어와 국가\/지역 이름 형식보다 운영 체제 업데이트에 의해 변경될 가능성이 적습니다.  
  
 `locale` 인수로 전달되는 null 포인터는 `setlocale`가 국제 환경을 설정하는 대신 쿼리하도록 지정합니다.  `locale` 인수가 null 포인터인 경우 프로그램의 현재 로캘 설정은 변경되지 않습니다.  대신 `setlocale`은 스레드의 현재 로캘인 `category`와 연결된 문자열에 대한 포인터를 반환합니다.  `category` 인수가 `LC_ALL`인 경우 함수가 세미콜론으로 구분된 각각의 범주의 현재 설정을 나타내는 문자열을 반환합니다.  예: 호출 시퀀스  
  
 `// Set all categories and return "en-US"`  
  
 `setlocale(LC_ALL, "en-US");`  
  
 `// Set only the LC_MONETARY category and return "fr-FR"`  
  
 `setlocale(LC_MONETARY, "fr-FR");`  
  
 `printf("%s\n", setlocale(LC_ALL, NULL));`  
  
 returns  
  
 `LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US`  
  
 `LC_ALL` 범주와 연결된 문자열입니다.  
  
 다음 예제는 `LC_ALL` 범주와 관련이 있습니다.  사용자 기본 OEM 코드 페이지 및 사용자 기본 ANSI 코드 페이지의 사용을 각각 지정하기 위해 코드 페이지 번호 대신 ".OCP" 및 ".ACP" 문자열을 사용할 수 있습니다.  
  
 `setlocale( LC_ALL, "" );`  
 로캘을 운영 체제에서 가져온 사용자 기본 ANSI 코드 페이지인 기본값으로 설정합니다.  
  
 `setlocale( LC_ALL, ".OCP" );`  
 로캘을 운영 체제에서 얻은 현재 OEM 코드 페이지로 명시적으로 설정합니다.  
  
 `setlocale( LC_ALL, ".ACP" );`  
 로캘을 운영 체제에서 얻은 ANSI 코드 페이지로 설정합니다.  
  
 `setlocale( LC_ALL, "<localename>" );`  
 로캘을 *\<localename\>*에 의해 표시되는 로캘 이름으로 설정합니다.  
  
 `setlocale( LC_ALL, "<language>_<country>" );`  
 호스트 운영 체제에서 가져온 기본 코드 페이지와 함께 로캘을 *\<language\>* 및 *\<country\>*에 의해 표시되는 언어 및 국가\/지역으로 설정합니다.  
  
 `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`  
 로캘을 *\<language\>*, *\<country\>* 및 *\<code\_page\>* 문자열에 의해 나타난 언어, 국가\/지역 및 코드 페이지를 나타내도록 설정합니다.  언어, 국가\/지역 및 코드 페이지의 다양한 조합을 사용할 수 있습니다.  예를 들어, 이 호출은 코드 페이지 1252에 따라 로캘을 프랑스어\(캐나다\)로 설정합니다.  
  
 `setlocale( LC_ALL, "French_Canada.1252" );`  
  
 이 호출은 기본 ANSI 코드 페이지에 따라 로캘을 프랑스어\(캐나다\)로 설정합니다.  
  
 `setlocale( LC_ALL, "French_Canada.ACP" );`  
  
 이 호출은 기본 OEM 코드 페이지에 따라 로캘을 프랑스어\(캐나다\)로 설정합니다.  
  
 `setlocale( LC_ALL, "French_Canada.OCP" );`  
  
 `setlocale( LC_ALL, "<language>" );`  
 로캘을 *\<language\>*에 의해 표시되는 언어로 설정하고 호스트 운영 체제에서 가져온 대로 지정된 언어 및 사용자 기본 ANSI 코드 페이지와 지정된 언어를 위한 기본 국가\/지역을 사용합니다.  예를 들어, `setlocale`에 대한 다음 호출은 기능적으로 동일합니다.  
  
 `setlocale( LC_ALL, "en-US" );`  
  
 `setlocale( LC_ALL, "English" );`  
  
 `setlocale( LC_ALL, "English_United States.1252" );`  
  
 성능 및 유지 관리에 첫 번째 폼을 사용하는 것이 좋습니다.  
  
 `setlocale( LC_ALL, ".<code_page>" );`  
 지정한 코드 페이지에 대한 기본 국가\/지역 및 언어\(호스트 운영 체제에 의해 정의됨\)와 함께 *\<code\_page\>*에 의해 표시되는 값으로 코드 페이지를 설정합니다.  
  
 코드 페이지에 변경 내용을 적용하려면 범주가 `LC_ALL` 또는 `LC_CTYPE`이어야 합니다.  예를 들어, 기본 국가\/지역 및 호스트 운영 체제의 언어가 "미국" 및 "영어"인 경우 `setlocale`에 대한 다음 두 호출이 기능적으로 동일합니다.  
  
 `setlocale( LC_ALL, ".1252" );`  
  
 `setlocale( LC_ALL, "English_United States.1252");`  
  
 자세한 내용은 [C\/C\+\+ 전처리기 참조](../../preprocessor/c-cpp-preprocessor-reference.md)에서 [setlocale](../../preprocessor/setlocale.md) pragma 지시문을 참조하십시오.  
  
 [\_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md) 함수는 `setlocale`가 프로그램의 모든 스레드 로캘 또는 호출 스레드의 로캘에 영향을 주는지의 여부를 제어하기 위해 사용됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`setlocale`|\<locale.h\>|  
|`_wsetlocale`|\<locale.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```css  
// crt_setlocale.c  
//   
// This program demonstrates the use of setlocale when  
// using two independent threads.  
//  
  
#include <locale.h>  
#include <process.h>  
#include <windows.h>  
#include <stdio.h>  
#include <time.h>  
  
#define BUFF_SIZE 100  
  
// Retrieve the date in the current  
// locale's format.  
int get_date(unsigned char* str)  
{  
    __time64_t ltime;  
    struct tm  thetime;  
  
    // Retrieve the current time  
    _time64(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    // Format the current time structure into a string  
    // "%#x" is the long date representation in the  
    // current locale  
    if (!strftime((char *)str, BUFF_SIZE, "%#x",   
                  (const struct tm *)&thetime))  
    {  
        printf("strftime failed!\n");  
        return -1;  
    }  
    return 0;  
}  
  
// This thread sets its locale to the argument  
// and prints the date.  
uintptr_t __stdcall SecondThreadFunc( void* pArguments )  
{  
    unsigned char str[BUFF_SIZE];  
    char * locale = (char *)pArguments;  
  
    // Set the thread locale  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, locale));  
  
    // Retrieve the date string from the helper function  
    if (get_date(str) == 0)  
    {  
        printf("The date in %s locale is: '%s'\n", locale, str);  
    }  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
// The main thread sets the locale to English   
// and then spawns a second thread (above) and prints the date.  
int main()  
{   
    HANDLE          hThread;  
    unsigned        threadID;  
    unsigned char   str[BUFF_SIZE];  
  
    // Configure per-thread locale to cause all subsequently created   
    // threads to have their own locale.  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
  
    // Set the locale of the main thread to US English.  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "en-US"));  
  
    // Create the second thread with a German locale.  
    // Our thread function takes an argument of the locale to use.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,  
                                      "de-DE", 0, &threadID );  
  
    if (get_date(str) == 0)  
    {  
        // Retrieve the date string from the helper function  
        printf("The date in en-US locale is: '%s'\n\n", str);  
    }  
  
    // Wait for the created thread to finish.  
    WaitForSingleObject( hThread, INFINITE );  
  
    // Destroy the thread object.  
    CloseHandle( hThread );  
}  
```  
  
  **현재 스레드 로캘이 en\-US로 설정되어 있습니다.**  
**en\-US 로캘의 시간: '2004년 5월 12일 수요일'**  
**현재 스레드 로캘이 de\-DE로 설정되어 있습니다.**  
**de\-DE 로캘의 시간: 'Mittwoch, 12.  Mai 2004'**    
## 해당 .NET Framework 항목  
 [System::Globalization::CultureInfo Class](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)  
  
## 참고 항목  
 [로캘 이름, 언어 및 국가\/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [\_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)