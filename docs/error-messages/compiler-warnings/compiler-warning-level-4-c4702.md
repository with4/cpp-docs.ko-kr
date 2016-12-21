---
title: "컴파일러 경고 (수준 4) C4702 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4702"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4702"
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4702
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

접근할 수 없는 코드입니다.  
  
 이 경고는 Visual Studio .NET 2003의 컴파일러 규칙에 따라 접근할 수 없는 코드가 발견되었기 때문에 발생합니다.  컴파일러\(백 엔드\)에서 접근할 수 없는 코드를 발견하면 수준 4 경고인 C4702가 발생합니다.  
  
 Visual Studio .NET 2003과 Visual Studio .NET 버전의 Visual C\+\+ 모두에서 올바른 코드가 되도록 하려면 접근할 수 없는 코드를 제거하거나 실행 흐름에서 모든 소스 코드에 접근할 수 있도록 하십시오.  
  
## 예제  
 다음 샘플에서는 C4702 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4702.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main() {  
   return 1;  
   printf_s("I won't print.\n");   // C4702 unreachable  
}  
```  
  
## 예제  
 **\/GX**, **\/EHc**, **\/EHsc** 또는 **\/EHac**를 사용하여 컴파일할 때 extern C 함수를 사용하는 경우 코드에 접근하지 못할 수 있습니다. extern C 함수가 throw되지 않는 것으로 간주하여 catch 블록에 액세스할 수 없기 때문입니다.  함수를 throw할 수 있으므로 이 경고가 불필요한 경우 throw된 예외에 따라 **\/EHa** 또는 **\/EHs**를 사용하여 컴파일하십시오.  
  
 자세한 내용은 [\/EH\(예외 처리 모델\)](../../build/reference/eh-exception-handling-model.md)를 참조하십시오.  
  
 다음 샘플에서는 C4702 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4702b.cpp  
// compile with: /W4 /EHsc  
#include <iostream>  
  
using namespace std;  
extern "C" __declspec(dllexport) void Function2(){}  
  
int main() {  
   try {  
      Function2();  
   }  
   catch (...) {  
      cout << "Exp: Function2!" << endl;   // C4702  
   }  
}  
```