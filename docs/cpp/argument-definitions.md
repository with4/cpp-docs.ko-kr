---
title: "인수 정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- envp argument
- main function, arguments
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4bb50f4471aed2af6de0ae20e2e3c85ab0cb5d9e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="argument-definitions"></a>인수 정의
프로토타입의 인수를 사용하면  
  
```  
  
int main( int  
argc[ ,char*argv[] [,char*envp[] ] ] );intwmain(intargc[ ,wchar_t*argv[] [,wchar_t*envp[] ] ] );  
```  
  
 인수를 편리하게 명령줄에서 구문 분석하고 선택적으로 환경 변수에 액세스할 수 있습니다. 인수 정의는 다음과 같습니다.  
  
 `argc`  
 `argv` 뒤에 오는 인수의 수를 포함하는 정수입니다. `argc` 매개 변수는 항상 1보다 크거나 같습니다.  
  
 `argv`  
 프로그램의 사용자가 입력한 명령줄 인수를 나타내는 null로 끝나는 문자열의 배열입니다. 규칙에 따라 `argv` **[0]** 된 프로그램을 호출, 명령 `argv` **[1]** 될 때까지 이런 식으로 확인 하 고 첫 번째 명령줄 인수는 `argv`  **[**`argc`**]**, 항상 **NULL**합니다. 참조 [명령줄 처리 사용자 지정](../cpp/customizing-cpp-command-line-processing.md) 명령줄 처리 억제에 대 한 내용은 합니다.  
  
 첫 번째 명령줄 인수는 항상 `argv` **[1]** 마지막 트랜잭션이 및 `argv` **[** `argc` -1**]**합니다.  
  
> [!NOTE]
>  규칙에 따라 `argv`**[0]**은 프로그램을 호출하는 데 사용하는 명령입니다.  그러나, 사용 하 여 프로세스를 생성할 수는 [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms683197) 첫 번째와 두 번째 인수를 사용 하는 경우 및 (`lpApplicationName` 및 `lpCommandLine`), `argv` **[0]** 되지 않을 수 있습니다는 실행 파일 이름입니다. 사용 하 여 [getmodulefilename이](http://msdn.microsoft.com/library/windows/desktop/ms683197) , 실행 파일 이름 및 전체 경로 검색할 수 있습니다.  
  
## <a name="microsoft-specific"></a>Microsoft 전용  
 `envp`  
 많은 UNIX 시스템에서 일반 확장인 `envp` 배열이 Microsoft C++에서 사용됩니다. 이는 사용자 환경에서 설정된 변수를 나타내는 문자열의 배열입니다. 이 배열은 종료 되는 한 **NULL** 항목입니다. 에 대 한 포인터의 배열으로 선언할 수 있습니다 **char (char** \*envp**)** 또는 포인터에 대 한 포인터로 **char (char** \* \* envp**)**합니다. 프로그램을 사용 하는 경우 **wmain** 대신 **주**를 사용 하 여는 `wchar_t` 데이터 형식 대신 `char`합니다. 에 전달 된 환경 블록 **주** 및 **wmain** 현재 환경의 "고정된" 복사본입니다. 호출을 통해 환경 변경 해도 **putenv** 또는 `_wputenv`, 현재 환경 (반환한 `getenv` / `_wgetenv` 및 `_environ` /  `_wenviron` 변수)는 변경 되지만 envp가 가리키는 블록은 변경 되지 것입니다. 참조 [명령줄 처리 사용자 지정](../cpp/customizing-cpp-command-line-processing.md) 환경 처리 억제에 대 한 내용은 합니다. 이 인수는 C에서는 ANSI와 호환되지만 C++에서는 호환되지 않습니다.  
  
**Microsoft 전용 종료**  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `argc`, `argv`, 및 `envp` 에 대 한 인수 **주**:  
  
```  
// argument_definitions.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
int main( int argc, char *argv[], char *envp[] ) {  
    int iNumberLines = 0;    // Default is no line numbers.  
  
    // If /n is passed to the .exe, display numbered listing  
    // of environment variables.  
  
    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )  
         iNumberLines = 1;  
  
    // Walk through list of strings until a NULL is encountered.  
    for( int i = 0; envp[i] != NULL; ++i ) {  
        if( iNumberLines )  
            cout << i << ": " << envp[i] << "\n";  
    }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [main: 프로그램 시작](../cpp/main-program-startup.md)