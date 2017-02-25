---
title: "컴파일러 경고 (수준 1) C4835 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4835"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4835"
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 경고 (수준 1) C4835
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : 내보낸 데이터의 이니셜라이저는 관리 코드가 호스트 어셈블리에서 먼저 실행되어야 실행됩니다.  
  
 관리되는 구성 요소 사이에서 데이터에 액세스하는 경우 네이티브 C\+\+ 가져오기 및 내보내기 메커니즘을 사용하지 않는 것이 좋습니다.  대신, 관리되는 형식 안에 데이터 멤버를 선언하고 클라이언트에서 `#using`을 사용하여 메타데이터를 참조하는 것이 좋습니다.  자세한 내용은 [\#using 지시문](../../preprocessor/hash-using-directive-cpp.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4835 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4835.cpp  
// compile with: /W1 /clr /LD  
int f() { return 1; }  
int n = 9;  
  
__declspec(dllexport) int m = f();   // C4835  
__declspec(dllexport) int *p = &n;   // C4835  
```  
  
## 예제  
 다음 샘플에서는 위 샘플에서 빌드한 구성 요소를 사용하여 변수의 값이 예상과 다르다는 것을 보여 줍니다.  
  
```  
// C4835_b.cpp  
// compile with: /clr C4835.lib  
#include <stdio.h>  
__declspec(dllimport) int m;  
__declspec(dllimport) int *p;  
  
int main() {  
   printf("%d\n", m);  
   printf("%d\n", p);  
}  
```  
  
  **0**  
**268456008**