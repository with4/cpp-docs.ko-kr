---
title: "_strdec, _wcsdec, _mbsdec, _mbsdec_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcsdec"
  - "_strdec"
  - "_mbsdec"
  - "_mbsdec_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_strdec"
  - "mbsdec_l"
  - "strdec"
  - "_mbsdec"
  - "_mbsdec_l"
  - "mbsdec"
  - "wcsdec"
  - "_wcsdec"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsdec 함수"
  - "_mbsdec_l 함수"
  - "_strdec 함수"
  - "_tcsdec 함수"
  - "_wcsdec 함수"
  - "mbsdec 함수"
  - "mbsdec_l 함수"
  - "strdec 함수"
  - "tcsdec 함수"
  - "wcsdec 함수"
ms.assetid: ae37c223-800f-48a9-ae8e-38c8d20af2dd
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _strdec, _wcsdec, _mbsdec, _mbsdec_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자열 포인터를 한 문자 뒤로 이동합니다.  
  
> [!IMPORTANT]
>  `mbsdec` 와 `mbsdec_l` 는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
unsigned char *_strdec(  
   const unsigned char *start,  
   const unsigned char *current   
);  
unsigned wchar_t *_wcsdec(  
   const unsigned wchar_t *start,  
   const unsigned wchar_t *current   
);  
unsigned char *_mbsdec(  
   const unsigned char *start,  
   const unsigned char *current   
);  
unsigned char *_mbsdec_l(  
   const unsigned char *start,  
   const unsigned char *current,  
   _locale_t locale  
);  
```  
  
#### 매개 변수  
 `start`  
 소스 문자열의 모든 문자\( `_mbsdec`  또는 \_`mbsdec_l`, 멀티 바이트 문자의 첫 번째 바이트\)에 대한 포인터입니다. `start`는 소스 문자열에서 반드시  `current`  의 앞에 위치해야합니다.  
  
 `current`  
 소스 문자열의 모든 문자\( `_mbsdec`  또는 \_`mbsdec_l`, 멀티 바이트 문자의 첫 번째 바이트\)에 대한 포인터입니다. `current`는 소스 문자열에서 반드시  `start`  의 뒤에 위치해야합니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## 반환 값  
 `_mbsdec`\_`mbsdec_l`,  `_strdec` , 및  `_wcsdec` 은 각각  `current`  바로 앞에있는 문자열의 포인터를 반환합니다.  `_mbsdec`는  `start` 의 값이  `current` 와 같거나 더 클 경우,  `NULL` 을 반환합니다.  `_tcsdec`은 이러한 함수 중 하나에 매핑되며, 해당 반환 값은 매핑에 따라 달라집니다.  
  
## 설명  
 `_mbsdec`  및  `_mbsdec_l`  함수는  `start` 이 포함된 문자열에서  `current`  바로 앞의 멀티 바이트 문자의 첫 번째 바이트에 대한 포인터를 반환합니다.  
  
 출력 값은 로케일의  `LC_CTYPE`  범주 설정의 설정에 의해 적용됩니다. 자세한 내용은 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) 을 참조하십시오.   `_mbsdec_l`  전달 된 로케일 매개 변수를 대신 사용하는 것을 제외하고 같은 반면에, `_mbsdec`는 현재 사용 중인 로케일에 따라 멀티 바이트 문자 시퀀스를 인식합니다.   자세한 내용은 [로캘](../../c-runtime-library/locale.md)을 참조하십시오.  
  
 만일 `start` 혹은 `current` 가 `NULL` 이라면, 잘못된 매개 변수 처리기가 호출됩니다. 이는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명되어 있습니다.  계속해서 실행하도록 허용된 경우, 이 함수는 `EINVAL` 를 반환하고 `errno` 를 `EINVAL`로 설정합니다.  
  
> [!IMPORTANT]
>  이러한 함수는 버퍼 오버런 위협에 노출될 수 있습니다.  버퍼 오버런은 불필요한 권한 상승을 발생시킬 수 있으므로 시스템 공격에 사용될 수 있습니다.  자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcsdec`|`_strdec`|`_mbsdec`|`_wcsdec`|  
  
 `_strdec` 와 `_wcsdec` 는 싱글 바이트 및 `_mbsdec` 와 `_mbsdec_l`의 와이드 바이트 문자 버전입니다.  `_strdec` 및 `_wcsdec` 는 매핑 경우에 제공 되고 그렇지 않으면 사용할 수 없습니다.  
  
 자세한 내용은 [일반 텍스트 매핑 사용](../../c-runtime-library/using-generic-text-mappings.md) 및 [일반 텍스트 매핑](../../c-runtime-library/generic-text-mappings.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_mbsdec`|\<mbstring.h\>|\<mbctype.h\>|  
|`_mbsdec_l`|\<mbstring.h\>|\<mbctype.h\>|  
|`_strdec`|\<tchar.h\>||  
|`_wcsdec`|\<tchar.h\>||  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `_tcsdec`를 사용하는 방법을 보여 줍니다.  
  
```  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main()  
{  
   const TCHAR *str = _T("12345");  
   cout << "str: " << str << endl;  
  
   const TCHAR *str2;  
   str2 = str + 2;  
   cout << "str2: " << str2 << endl;  
  
   TCHAR *answer;  
   answer = _tcsdec( str, str2 );  
   cout << "answer: " << answer << endl;  
  
   return (0);   
}  
  
```  
  
 다음 예제에서는 `_mbsdec`를 사용하는 방법을 보여 줍니다.  
  
```  
#include <iostream>  
#include <mbstring.h>  
using namespace std;  
  
int main()   
{   
   char *str = "12345";  
   cout << "str: " << str << endl;  
  
   char *str2;  
   str2 = str + 2;   
   cout << "str2: " << str2 << endl;  
  
   unsigned char *answer;  
   answer = _mbsdec( reinterpret_cast<unsigned char *>( str ), reinterpret_cast<unsigned char *>( str2 ));  
  
   cout << "answer: " << answer << endl;  
  
   return (0);   
}  
  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [\_strinc, \_wcsinc, \_mbsinc, \_mbsinc\_l](../../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)   
 [\_strnextc, \_wcsnextc, \_mbsnextc, \_mbsnextc\_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)   
 [\_strninc, \_wcsninc, \_mbsninc, \_mbsninc\_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)