---
title: "C++ 명령줄 인수 구문 분석 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인용 부호 및 명령줄 인수"
  - "큰따옴표"
  - "명령줄을 구문 분석"
  - "구문 분석, 명령줄 인수"
  - "시작 코드의 경우 명령줄 인수 구문 분석"
ms.assetid: e634e733-ac2f-4298-abe2-7e9288c94951
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 명령줄 인수 구문 분석
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 Microsoft C/c + + 시작 코드는 운영 체제 명령줄에 지정 된 인수를 해석할 때 다음 규칙을 사용 합니다.  
  
-   인수를 공백이나 탭으로 구분합니다.  
  
-   캐럿 (^) 문자는 이스케이프 문자나 구분 기호로 인식할 수 없습니다. 문자는 완전히 처리 운영 체제의 명령줄 파서에서 전달 되기 전에 `argv` 프로그램의 배열입니다.  
  
-   큰따옴표로 묶은 문자열 ("*문자열*") 내에 포함 된 공백에 상관 없이 하나의 인수로 해석 됩니다. 따옴표로 묶은 문자열은 인수에 포함될 수 있습니다.  
  
-   백슬래시는 큰따옴표 (\\")는 리터럴 큰따옴표 문자 (")로 해석 됩니다.  
  
-   백슬래시는 큰따옴표 바로 앞에 있지 않으면 리터럴로 해석됩니다.  
  
-   하나 이상의 백슬래시에 배치 됩니다 오는 경우는 짝수 개의 백슬래시는 큰따옴표는 `argv` 배열, 백슬래시 쌍 마다 및 큰따옴표는 문자열 구분 기호로 해석 됩니다.  
  
-   하나 이상의 백슬래시에 배치 됩니다 오는 경우 홀수 개의 백슬래시는 큰따옴표는 `argv` 배열, 백슬래시 쌍 마다 및 큰따옴표는 "이스케이프" 백슬래시로 나머지는 리터럴 큰따옴표 (")에 배치 될 `argv`합니다.  
  
## <a name="example"></a>예제  
 다음 프로그램은 어떻게 명령줄 인수를 보여 줍니다. 전달 됩니다.  
  
```  
// command_line_arguments.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
int main( int argc,      // Number of strings in array argv  
          char *argv[],   // Array of command-line argument strings  
          char *envp[] )  // Array of environment variable strings  
{  
    int count;  
  
    // Display each command-line argument.  
    cout << "\nCommand-line arguments:\n";  
    for( count = 0; count < argc; count++ )  
         cout << "  argv[" << count << "]   "  
                << argv[count] << "\n";  
}  
```  
  
 다음 표에서 예제에서는 입력 및 앞의 목록에서 규칙을 설명 하는 예상된 출력을 보여 줍니다.  
  
### <a name="results-of-parsing-command-lines"></a>명령줄을 구문 분석 한 결과  
  
|명령줄 입력|argv[1]|argv [2]|argv [3]|  
|-------------------------|---------------|---------------|---------------|  
|`"abc" d e`|`abc`|`d`|`e`|  
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|  
|`a\\\"b c d`|`a\"b`|`c`|`d`|  
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|  
  
## <a name="end-microsoft-specific"></a>Microsoft 전용 종료  
  
## <a name="see-also"></a>참고 항목  
 [main: 프로그램 시작](../cpp/main-program-startup.md)