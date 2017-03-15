---
title: "함수 이름을 () 없이 사용하면 코드가 생성되지 않음 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "함수[C++], 괄호 없이 사용"
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 함수 이름을 () 없이 사용하면 코드가 생성되지 않음
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램에서 선언된 함수 이름을 괄호 없이 사용하면 컴파일러에서 코드를 생성하지 않습니다.   이러한 결과는 매개 변수 사용 여부에 관계없이 발생하는데, 컴파일러에서 함수 주소를 계산하지만 함수 호출 연산자인 “\(\)”가 없기 때문에 호출은 이루어지지 않습니다.  이 결과는 다음과 유사합니다.  
  
```  
// compile with /Wall to generate a warning  
int a;  
a;      // no code generated here either  
```  
  
 Visual C\+\+에서는 경고 수준 4를 사용하는 경우에도 진단 결과가 생성되지 않습니다.  경고 메시지도 나타나지 않고 코드도 생성되지 않습니다.  
  
 다음 예제 코드에서는 경고와 함께 컴파일하고 오류 없이 제대로 링크되지만 `funcn( )`에 관한 코드는 생성하지 않습니다.  이 코드가 올바르게 작동되도록 하려면 함수 호출 연산자인 "\(\)"를 추가하십시오.  
  
```  
#include <stdio.h>  
void funcn();  
  
int main() {  
   funcn;      /* missing function call operator;   
                  call will fail.  Use funcn() */  
   }  
  
void funcn() {  
   printf("\nHello World\n");  
}  
```  
  
## 참고 항목  
 [코드 최적화](../../build/reference/optimizing-your-code.md)