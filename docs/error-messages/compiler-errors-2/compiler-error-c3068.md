---
title: "컴파일러 오류 C3068 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3068"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3068"
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3068
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 'naked' 함수는 C\+\+ 예외가 발생했을 때 해제가 필요한 개체를 포함할 수 없습니다.  
  
 예외를 throw한 [naked](../../cpp/naked-cpp.md) 함수에 대한 스택 해제를 컴파일러에서 수행할 수 없습니다. 함수에 임시 개체가 작성되었고 C\+\+ 예외 처리\([\/EHsc](../../build/reference/eh-exception-handling-model.md)\)를 지정했기 때문입니다.  
  
 이 오류를 해결하려면 다음 중 하나를 수행하십시오.  
  
-   \/EHsc를 사용하여 컴파일하지 마십시오.  
  
-   함수를 `naked`로 표시하지 마십시오.  
  
-   함수에 임시 개체를 만들지 마십시오.  
  
 함수의 임시 개체가 스택에 작성되거나 함수에서 예외가 throw되거나 C\+\+ 예외 처리가 활성화된 경우 컴파일러는 예외가 throw될 때 스택을 정리합니다.  
  
 예외가 throw되면 컴파일러에서 생성된 코드가 함수에 대해 실행됩니다. 이 코드는 naked 함수에 없는 프롤로그와 에필로그를 호출합니다.  
  
## 예제  
 다음 샘플에서는 C3068 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3068.cpp  
// compile with: /EHsc  
// processor: x86  
class A {  
public:  
   A(){}  
   ~A(){}  
};  
  
void b(A){}  
  
__declspec(naked) void c() {  
   b(A());   // C3068   
};  
```