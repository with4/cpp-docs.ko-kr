---
title: "assert 매크로, _assert, _wassert | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- assert
- _assert
- _wassert
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- assert
- _assert
- _wassert
- assert/_wassert
dev_langs:
- C++
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ad3410852975757c34220e2de19f696ba3b7c718
ms.lasthandoff: 02/24/2017

---
# <a name="assert-macro-assert-wassert"></a>assert Macro, _assert, _wassert
식을 계산하고 결과가 `false`이면 진단 메시지를 출력하고 프로그램을 중단합니다.  
  
## <a name="syntax"></a>구문  
  
```  
assert(   
   expression   
);  
void _assert(  
   char const* message,  
   char const* filename,  
   unsigned line  
);  
void _wassert(  
   wchar_t const* message,  
   wchar_t const* filename,  
   unsigned line  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `expression`  
 0이 아닌 값(`true`) 또는 0(`false`)으로 계산되는 스칼라 식(포인터 식 포함)입니다.  
  
 `message`  
 표시할 메시지입니다.  
  
 `filename`  
 어설션이 실패한 소스 파일의 이름입니다.  
  
 `line`  
 실패한 어설션의 소스 파일에 있는 줄 번호입니다.  
  
## <a name="remarks"></a>설명  
 일반적으로 `assert` 매크로는 프로그램을 개발하는 동안 논리 오류를 식별하는 데 사용됩니다. 이 매크로를 사용하여 프로그램이 잘못 작동할 때만 `expression` 로 계산되도록 `false` 인수를 구현하는 방식으로 예기치 않은 조건이 발생할 때 프로그램 실행을 중지합니다. 컴파일 시간에 매크로 `NDEBUG`를 정의하여 어설션 검사를 끌 수 있습니다. `assert` 명령줄 옵션을 사용하여 소스 파일을 수정하지 않고 **assert** 매크로를 끌 수 있습니다. \<assert.h>를 포함하기 전에 `#define NDEBUG` 지시문을 사용하여 소스 코드에서 `assert` 매크로를 끌 수 있습니다.  
  
 `assert` 매크로는 `expression`이 `false`(0)이면 진단 메시지를 출력하고 [abort](../../c-runtime-library/reference/abort.md)를 호출하여 프로그램 실행을 종료합니다. `expression` 이 `true` (0이 아닌 값)이면 아무 작업도 수행되지 않습니다. 진단 메시지에는 실패한 식, 소스 파일의 이름 및 어설션이 실패한 줄의 번호가 포함됩니다.  
  
 진단 메시지는 와이드 문자로 출력됩니다. 따라서 식에 유니코드 문자가 있어도 예상대로 작동합니다.  
  
 진단 메시지의 대상은 루틴을 호출한 응용 프로그램의 형식에 따라 달라집니다. 콘솔 응용 프로그램은 항상 `stderr`을 통해 메시지를 받습니다. Windows 기반 응용 프로그램에서는 `assert` 가 Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) 함수를 호출하여 **OK** 단추와 함께 메시지를 표시하는 메시지 상자를 만듭니다. 사용자가 **확인**을 클릭하면 프로그램이 즉시 중단됩니다.  
  
 응용 프로그램이 런타임 라이브러리의 디버그 버전과 연결되어 있으면 `assert` 가 **중단**, **다시 시도**및 **무시**라는 세 가지 단추가 포함된 메시지 상자를 만듭니다. 사용자가 **중단**을 클릭하면 프로그램이 즉시 중단됩니다. 사용자가 **다시 시도**를 클릭하면 디버거가 호출되고 JIT(Just-In-Time) 디버깅을 사용하는 경우 사용자가 프로그램을 디버깅할 수 있습니다. 사용자가 **무시**를 클릭하면 `assert` 가 **확인** 단추가 포함된 메시지 상자를 만들며 정상적인 실행을 계속합니다. 오류 조건이 있을 때 **무시** 를 클릭하면 정의되지 않은 동작이 발생할 수 있습니다.  
  
 CRT 디버깅에 대한 자세한 내용은 [CRT 디버깅 기술](/visualstudio/debugger/crt-debugging-techniques)을 참조하세요.  
  
 `_assert` 및 `_wassert` 함수는 내부 CRT 함수입니다. 이를 통해 어설션을 지원하기 위해 개체 파일에 필요한 코드를 최소화할 수 있습니다. 이들 함수는 직접 호출하지 않는 것이 좋습니다.  
  
 `assert` 가 정의되지 않으면 `NDEBUG` 매크로는 C 런타임 라이브러리의 릴리스 및 디버그 버전에서 모두 사용하도록 설정됩니다. `NDEBUG` 가 정의되면 매크로를 사용할 수 있지만 매크로가 인수를 계산하지 않고 아무런 영향을 주지 않습니다. 사용하도록 설정되면 `assert` 매크로가 구현을 위해 `_wassert` 를 호출합니다. 기타 어셜션 매크로 [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 및 [_ASSERT_EXPR](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)도 사용할 수 있지만 어설션 매크로는 [_DEBUG](../../c-runtime-library/debug.md) 매크로가 정의되고 어설션 매크로가 C 런타임 라이브러리의 디버그 버전과 연결된 코드에 있을 때만 어설션 매크로에 전달되는 식을 계산합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`assert`, `_wassert`|\<assert.h>|  
  
 `_assert` 함수의 서명은 헤더 파일에서 사용할 수 없습니다. `_wassert` 함수의 서명은 `NDEBUG` 매크로가 정의되지 않았을 때만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 프로그램에서 `analyze_string` 함수는 `assert` 매크로를 사용하여 문자열 및 길이와 관련된 여러 조건을 테스트합니다. 조건 중 하나라도 실패하면 프로그램이 실패의 원인을 나타내는 메시지를 출력합니다.  
  
```  
// crt_assert.c  
// compile by using: cl /W4 crt_assert.c  
#include <stdio.h>  
#include <assert.h>  
#include <string.h>  
  
void analyze_string( char *string );   // Prototype  
  
int main( void )  
{  
   char  test1[] = "abc", *test2 = NULL, test3[] = "";  
  
   printf ( "Analyzing string '%s'\n", test1 ); fflush( stdout );  
   analyze_string( test1 );  
   printf ( "Analyzing string '%s'\n", test2 ); fflush( stdout );  
   analyze_string( test2 );  
   printf ( "Analyzing string '%s'\n", test3 ); fflush( stdout );  
   analyze_string( test3 );  
}  
  
// Tests a string to see if it is NULL,   
// empty, or longer than 0 characters.  
void analyze_string( char * string )  
{  
   assert( string != NULL );        // Cannot be NULL  
   assert( *string != '\0' );       // Cannot be empty  
   assert( strlen( string ) > 2 );  // Length must exceed 2  
}  
```  
  
 프로그램에서 다음 출력이 생성됩니다.  
  
```Output  
Analyzing string 'abc'  
Analyzing string '(null)'  
Assertion failed: string != NULL, file crt_assert.c, line 25  
```  
  
 어설션 실패 후에는 운영 체제 및 런타임 라이브러리의 버전에 따라 다음과 같은 내용이 포함된 메시지 상자가 표시될 수 있습니다.  
  
```Output  
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.  
```  
  
 디버거가 설치되어 있으면 **디버그** 단추를 선택하여 디버거를 시작하거나, **프로그램을 닫아** 종료합니다.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 [System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## <a name="see-also"></a>참고 항목  
 [오류 처리](../../c-runtime-library/error-handling-crt.md)   
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [raise](../../c-runtime-library/reference/raise.md)   
 [signal](../../c-runtime-library/reference/signal.md)   
 [_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)   
 [_DEBUG](../../c-runtime-library/debug.md)
