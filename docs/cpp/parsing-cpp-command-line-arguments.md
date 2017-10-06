---
title: "C + + 명령줄 인수 구문 분석 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- command line [C++], parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: e634e733-ac2f-4298-abe2-7e9288c94951
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5d3fbcd6b4e92d6e445d78a1b36efae319e472d7
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="parsing-c-command-line-arguments"></a>C++ 명령줄 인수 구문 분석
**Microsoft 전용**  
  
 Microsoft C/c + + 시작 코드는 다음 규칙을 사용 하 여 운영 체제 명령줄에 지정 된 인수를 해석할 때:  
  
-   인수를 공백이나 탭으로 구분합니다.  
  
-   캐럿 문자(^)는 이스케이프 문자나 구분 기호로 인식되지 않습니다. 문자는 완전히 처리 운영 체제의 명령줄 파서에서 전달 되기 전에 `argv` 프로그램의 배열입니다.  
  
-   큰따옴표로 묶은 문자열 ("*문자열*") 내에 포함 된 공백에 상관 없이 하나의 인수로 해석 됩니다. 따옴표로 묶은 문자열은 인수에 포함될 수 있습니다.  
  
-   백슬래시 다음의 큰따옴표(\\")는 리터럴 큰따옴표 문자(")로 해석됩니다.  
  
-   백슬래시는 큰따옴표 바로 앞에 있지 않으면 리터럴로 해석됩니다.  
  
-   하나 이상의 백슬래시에 위치한 짝수 개수의 백슬래시 뒤에 큰따옴표가 있으면는 `argv` 큰따옴표 및 백슬래시 모든 쌍에 대 한 배열 문자열 구분 기호로 해석 됩니다.  
  
-   하나 이상의 백슬래시에 위치한 백슬래시 수가 홀수인 뒤에 큰따옴표가 있으면는 `argv` 큰따옴표 및 백슬래시 모든 쌍에 대 한 배열 "이스케이프 된" 백슬래시로 나머지는 리터럴 큰따옴표 (" )에 배치 될 `argv`합니다.  
  
## <a name="example"></a>예제  
 다음 프로그램 방법을 명령줄 인수를 보여 줍니다. 전달 됩니다.  
  
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
  
 다음 표에서 예에서는 입력 및 앞의 목록에 규칙을 보여 주는 예상된 출력을 보여 줍니다.  
  
### <a name="results-of-parsing-command-lines"></a>명령줄 구문 분석 한 결과  
  
|명령줄 입력|argv[1]|argv[2]|argv[3]|  
|-------------------------|---------------|---------------|---------------|  
|`"abc" d e`|`abc`|`d`|`e`|  
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|  
|`a\\\"b c d`|`a\"b`|`c`|`d`|  
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [main: 프로그램 시작](../cpp/main-program-startup.md)
