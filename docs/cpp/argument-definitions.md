---
title: "인수 정의 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "argc 인수"
  - "인수[C++], main 함수용"
  - "argv 인수"
  - "envp 인수"
  - "main 함수, 인수"
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 인수 정의
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로토타입의 인수를 사용하면  
  
```  
  
int main( int argc[ , char *argv[ ] [, char *envp[ ] ] ] ); int wmain( int argc[ , wchar_t *argv[ ] [, wchar_t *envp[ ] ] ] );  
```  
  
 인수를 편리하게 명령줄에서 구문 분석하고 선택적으로 환경 변수에 액세스할 수 있습니다.  인수 정의는 다음과 같습니다.  
  
 `argc`  
 `argv` 뒤에 오는 인수의 수를 포함하는 정수입니다.  `argc` 매개 변수는 항상 1보다 크거나 같습니다.  
  
 `argv`  
 프로그램의 사용자가 입력한 명령줄 인수를 나타내는 null로 끝나는 문자열의 배열입니다.  규칙에 따라 `argv`**\[0\]**은 프로그램을 호출하는 데 사용하는 명령이고 `argv`**\[1\]**은 첫 번째 명령줄 인수가 되는 방식으로 `argv`**\[**`argc`**\]**\(항상 **NULL**임\)까지 진행됩니다.  명령줄 처리 억제에 대한 자세한 내용은 [명령줄 처리 사용자 지정](../cpp/customizing-cpp-command-line-processing.md)을 참조하십시오.  
  
 첫 번째 명령줄 인수는 항상 `argv`**\[1\]**이고 마지막은 `argv`**\[**`argc` – 1**\]**입니다.  
  
> [!NOTE]
>  규칙에 따라 `argv`**\[0\]**은 프로그램을 호출하는 데 사용하는 명령입니다.  그러나 [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms683197)를 사용하여 프로세스를 생성할 수 있으며, 첫 번째 인수와 두 번째 인수\(`lpApplicationName` 및 `lpCommandLine`\)를 모두 사용하는 경우 `argv`**\[0\]**이 실행 파일 이름이 아닐 수 있습니다. 실행 파일 이름 및 정규화된 경로를 검색하려면 [GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197)을 사용하십시오.  
  
## Microsoft 전용  
 `envp`  
 많은 UNIX 시스템에서 일반 확장인 `envp` 배열이 Microsoft C\+\+에서 사용됩니다.  이는 사용자 환경에서 설정된 변수를 나타내는 문자열의 배열입니다.  이 배열은 **NULL** 항목으로 종료됩니다.  이 배열은 **char\(char** \*envp\[ \]**\)**에 대한 포인터의 배열 또는 **char\(char** \*\*envp**\)** 포인터에 대한 포인터로 선언할 수 있습니다.  프로그램에서 **main** 대신 **wmain**을 사용하는 경우 `char` 대신 `wchar_t` 데이터 형식을 사용하십시오.  **main** 및 **wmain**으로 전달되는 환경 블록은 현재 환경의 "고정된" 복사본입니다.  이후에 **putenv** 또는 `_wputenv`에 대한 호출을 통해 환경을 변경하면 현재 환경\(`getenv`\/`_wgetenv` 및 `_environ`\/ `_wenviron` 변수에서 반환\)이 변경되지만 envp가 가리키는 블록은 변경되지 않습니다.  환경 처리 억제에 대한 자세한 내용은 [명령줄 처리 사용자 지정](../cpp/customizing-cpp-command-line-processing.md)을 참조하십시오.  이 인수는 C에서는 ANSI와 호환되지만 C\+\+에서는 호환되지 않습니다.  
  
## Microsoft 전용 종료  
  
## 예제  
 다음 예제에서는 `argc`, `argv` 및 `envp` 인수를 **main**에 사용하는 방법을 보여 줍니다.  
  
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
  
## 참고 항목  
 [main: 프로그램 시작](../cpp/main-program-startup.md)