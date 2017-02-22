---
title: "컴파일러 경고 (수준 1) C4342 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4342"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4342"
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 경고 (수준 1) C4342
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

동작 변경: 'function'이\(가\) 호출되었지만 이전 버전에서는 멤버 연산자가 호출되었습니다.  
  
 이전 버전의 Visual C\+\+에서는 멤버를 호출했지만 이 동작이 변경되었습니다. 이제 컴파일러는 네임스페이스 범위에서 가장 적합한 일치 항목을 찾습니다.  
  
 멤버 연산자를 찾은 경우 이전에는 컴파일러가 어떠한 네임스페이스 범위 연산자도 고려하지 않았습니다.  네임스페이스 범위에 더 적절한 일치 항목이 있는 경우 새 버전의 컴파일러는 이를 올바르게 호출하는 반면 이전 버전의 컴파일러는 이를 고려하지 않습니다.  
  
 이 경고는 코드를 현재 버전으로 올바르게 이식하면 해제됩니다.  컴파일러의 잘못된 확인으로 인해 동작이 변경되지 않은 코드에 대해 이 경고가 표시될 수도 있습니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하십시오.  
  
 다음 샘플에서는 C4342 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4342.cpp  
// compile with: /EHsc /W1  
#include <fstream>  
#pragma warning(default: 4342)  
using namespace std;  
struct X : public ofstream {  
   X();  
};  
  
X::X() {  
   open( "ofs_bug_ev.txt." );  
   if ( is_open() ) {  
      *this << "Text" << "<-should be text" << endl;   // C4342  
      *this << ' ' << "<-should be space symbol" << endl;   // C4342  
   }  
}  
  
int main() {  
   X b;  
   b << "Text" << "<-should be text" << endl;  
   b << ' ' << "<-should be space symbol" << endl;  
}  
```