---
title: "컴파일러 오류 C2065 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2065"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2065"
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# 컴파일러 오류 C2065
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 선언되지 않은 식별자입니다.  
  
 사용하려면 먼저 변수의 형식을 선언에서 지정해야 합니다.  함수에 사용되는 매개 변수를 선언 또는 프로토타입에서 지정해야 함수를 사용할 수 있습니다.  
  
 가능한 원인:  
  
1.  식별자 이름의 철자가 틀렸습니다.  
  
2.  식별자에 잘못된 대\/소문자가 사용되었습니다.  
  
3.  문자열 상수 뒤에 닫는 따옴표가 없습니다.  
  
4.  디버그 버전의 C 런타임을 사용해 컴파일하고 있으며 `for` 루프에서 선언한 표준 C\+\+ 라이브러리 반복기 변수를 `for` 루프 범위 밖에서 사용하려고 합니다.  디버그 버전의 C 런타임을 사용해 C\+\+ 표준 라이브러리 코드를 컴파일하는 경우 범위는 [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)입니다.  자세한 내용은 [디버그 반복기 지원](../../standard-library/debug-iterator-support.md)을 참조하세요.  
  
5.  사용하는 빌드 환경에서 현재 지원되지 않는 SDK 헤더 파일의 함수를 호출 중일 수 있습니다.  
  
6.  필수 포함 파일이 없습니다\(특히 `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN` 또는 `WIN32_EXTRA_LEAN`을 정의하는 경우\).  이 기호는 컴파일 속도를 높이기 위해 windows.h 및 afxv\_w32.h에서 일부 헤더 파일을 제외시킵니다.  \(windows.h 및 afxv\_w32.h를 참조하여 제외되는 파일에 대한 최신 설명을 확인하세요.\)  
  
7.  네임스페이스 범위가 잘못되었습니다.  예를 들어 정규화되지 않은 C\+\+ 표준 라이브러리 함수 및 연산자를 확인하려면 `using` 지시문을 사용하여 `std` 네임스페이스를 지정해야 합니다.  다음 예제에서는 `using` 지시문이 주석 처리되어 있고 `std` 네임스페이스에 `cout`가 정의되어 있기 때문에 컴파일하지 못합니다.  
  
## 예제  
 다음 샘플에서는 C2065 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2065.cpp  
// compile with: /EHsc  
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
   cout << "Hello" << endl;   // C2065  
  
   // Or try the following line instead  
   std::cout << "Hello" << std::endl;  
}  
```  
  
## 예제  
 제네릭 함수를 호출할 때 사용되는 매개 변수에서 원하는 형식 인수를 추론할 수 없는 경우 컴파일러는 오류를 보고합니다.  자세한 내용은 [Generic Functions \(C\+\+\/CLI\)](../../windows/generic-functions-cpp-cli.md)를 참조하세요.  
  
 다음 샘플에서는 C2065 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2065_b.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);   // C2065  
   G<int>(10);   // OK - fix with a specific type argument  
}  
```  
  
## 예제  
 이 오류는 Visual C\+\+ 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성될 수도 있습니다. 매개 변수에 Visual C\+\+ 특성이 있는지 확인합니다.  
  
 다음 샘플에서는 C2065 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2065_c.cpp  
// compile with: /c  
[module(DLL, name=MyLibrary)];   // C2065  
// try the following line instead  
// [module(dll, name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```