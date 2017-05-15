---
title: _ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ungetch_nolock
- _ungetwch_nolock
- _ungetwch
- _ungetch
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
- ucrtbase.dll
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ungetch_nolock
- ungetwch
- ungetch_nolock
- _ungetwch
- ungetch
- ungetwch_nolock
- _ungetch
- _ungettch_nolock
- _ungettch
- _ungetwch_nolock
dev_langs:
- C++
helpviewer_keywords:
- _ungetch function
- ungetwch function
- characters, pushing back to console
- _ungettch_nolock function
- ungettch function
- _ungettch function
- ungetch_nolock function
- ungettch_nolock function
- _ungetwch_nolock function
- _ungetch_nolock function
- ungetwch_nolock function
- _ungetwch function
ms.assetid: 70ae71c6-228c-4883-a57d-de6d5f873825
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 4c36da30cfc69140a47e779025acb579bb687df2
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="ungetch-ungetwch-ungetchnolock-ungetwchnolock"></a>_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock
콘솔에서 읽은 마지막 문자를 다시 푸시합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int _ungetch(  
   int c   
);  
wint_t _ungetwch(  
   wint_t c   
);  
int _ungetch_nolock(  
   int c   
);  
wint_t _ungetwch_nolock(  
   wint_t c   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `c`  
 푸시할 문자 수입니다.  
  
## <a name="return-value"></a>반환 값  
 두 함수는 모두 정상적으로 실행되는 경우 `c` 문자를 반환합니다. 오류가 발생 하는 경우 `_ungetch` 의 값을 반환 `EOF` 및 `_ungetwch` 반환 `WEOF`합니다.  
  
## <a name="remarks"></a>설명  
 이러한 함수는 문자 푸시 `c` 콘솔에 다시 일으키는 `c` 읽을 다음 문자를 `_getch` 또는 `_getche` (또는 `_getwch` 또는 `_getwche`). `_ungetch` 및 `_ungetwch`는 다음 읽기 이전에 여러 번 호출되면 실패합니다. `c` 인수는 `EOF` 또는 `WEOF`일 수 없습니다.  
  
 `_nolock` 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 점을 제외하면 동일합니다. 이러한 버전에서는 다른 스레드를 잠그는 오버헤드가 발생하지 않으므로 속도가 더 빠를 수 있습니다. 단일 스레드 응용 프로그램과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ungettch`|`_ungetch`|`_ungetch`|`_ungetwch`|  
|`_ungettch_nolock`|`_ungetch_nolock`|`_ungetch_nolock`|`_ungetwch_nolock`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_ungetch`, `_ungetch_nolock`|\<conio.h>|  
|`_ungetwch`, `_ungetwch_nolock`|\<conio.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_ungetch.c  
// compile with: /c  
// In this program, a white-space delimited   
// token is read from the keyboard. When the program   
// encounters a delimiter, it uses _ungetch to replace   
// the character in the keyboard buffer.  
//  
  
#include <conio.h>  
#include <ctype.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char buffer[100];  
   int count = 0;  
   int ch;  
  
   ch = _getche();  
   while( isspace( ch ) )      // Skip preceding white space.  
      ch = _getche();  
   while( count < 99 )         // Gather token.  
   {  
      if( isspace( ch ) )      // End of token.  
         break;  
      buffer[count++] = (char)ch;  
      ch = _getche();  
   }  
   _ungetch( ch );            // Put back delimiter.  
   buffer[count] = '\0';      // Null terminate the token.  
   printf( "\ntoken = %s\n", buffer );  
}  
```  
  
```Output  
  
Whitetoken = White  
```  
  
## <a name="see-also"></a>참고 항목  
 [콘솔 및 포트 I/O](../../c-runtime-library/console-and-port-i-o.md)   
 [_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)
