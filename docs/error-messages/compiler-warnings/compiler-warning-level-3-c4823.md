---
title: "컴파일러 경고 (수준 3) C4823 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4823"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4823"
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 경고 (수준 3) C4823
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 고정 포인터를 사용하지만 해제 의미 체계가 활성화되지 않았습니다.\/EHa를 사용하십시오.  
  
 블록 범위에 선언된 고정 포인터가 가리키는 관리되는 힙에 있는 개체를 고정 해제하기 위해 컴파일러에서는 고정 포인터에 포인터를 무효화하는 소멸자가 있는 것처럼 위장하는 방식으로 지역 클래스의 소멸자 동작을 시뮬레이션합니다.  예외를 throw한 후 소멸자를 호출할 수 있도록 하려면 [\/EHsc](../../build/reference/eh-exception-handling-model.md)를 사용하여 개체 해제 기능을 활성화해야 합니다.  
  
 수동으로 개체를 해제하고 경고를 무시할 수도 있습니다.  
  
## 예제  
 다음 샘플에서는 C4823 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4823.cpp  
// compile with: /clr /W3 /EHa-  
using namespace System;  
  
ref struct G {  
   int m;  
};  
  
void f(G ^ pG) {  
   try {  
      pin_ptr<int> p = &pG->m;  
      // manually unpin, ignore warning  
      // p = nullptr;  
      throw gcnew Exception;  
   }  
   catch(Exception ^) {}  
}   // C4823 warning  
  
int main() {  
   f( gcnew G );  
}  
```  
  
## 예제  
 **\/clr:oldSyntax**를 사용하는 경우에도 C4823이 발생할 수 있습니다.  다음 샘플에서는 C4823 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4823_b.cpp  
// compile with: /clr:oldSyntax /W3 /EHa-  
using namespace System;  
  
__gc struct G {  
   int m;  
};  
  
void f(G* pG) {  
   try {  
      int __pin* p = &pG->m;  
      // manually unpin, ignore warning  
      // p = 0;  
      throw new Exception;  
   }  
   catch(Exception*) {}  
}   // C4823  
  
int main() {  
   f( new G );  
}  
```