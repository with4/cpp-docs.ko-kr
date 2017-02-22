---
title: "컴파일러 경고 (수준 1) C4005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4005"
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 매크로 재정의  
  
 매크로 식별자가 두 번 정의되었습니다.  컴파일러는 둘째 매크로 정의를 사용합니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  `#define` 지시문이 포함된 코드 및 명령줄에서 매크로를 정의했습니다.  
  
2.  매크로를 포함 파일에서 가져왔습니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  정의 중 하나를 제거합니다.  
  
2.  둘째 정의 앞에 [\#undef](../../preprocessor/hash-undef-directive-c-cpp.md) 지시문을 사용합니다.  
  
 다음 샘플에서는 C4005 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4005.cpp  
// compile with: /W1 /EHsc  
#include <iostream>  
using namespace std;  
  
#define TEST "test1"  
#define TEST "test2"   // C4005 delete or rename to resolve the warning  
  
int main() {  
   cout << TEST << endl;  
}  
```