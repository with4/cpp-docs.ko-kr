---
title: "컴파일러 경고 (수준 1) C4715 | Microsoft Docs"
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
  - "C4715"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4715"
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4715
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 모든 제어 경로에서 값을 반환하지는 않습니다.  
  
 지정된 함수에서 값을 반환하지 않을 가능성이 있습니다.  
  
## 예제  
  
```  
// C4715a.cpp  
// compile with: /W1 /LD  
int func1( int i )  
{  
   if( i )  
   return 3;  // C4715 warning, nothing returned if i == 0  
}  
```  
  
 이 경고가 발생하지 않도록 하려면 코드를 수정하여 모든 경로에서 함수에 대한 반환 값을 할당하도록 하십시오.  
  
```  
// C4715b.cpp  
// compile with: /LD  
int func1( int i )  
{  
   if( i ) return 3;  
   else return 0;     // OK, always returns a value  
}  
```  
  
 코드에 다음 예제와 같이 값을 반환하지 않는 함수에 대한 호출이 있을 수 있습니다.  
  
```  
// C4715c.cpp  
// compile with: /W1 /LD  
void fatal()  
{  
}  
int glue()  
{  
   if(0)  
      return 1;  
   else if(0)  
      return 0;  
   else  
      fatal();   // C4715  
}  
```  
  
 컴파일러에서는 `fatal`이 값을 반환하지 않는다는 것을 알지 못하므로 이 코드에서도 경고가 발생합니다.  이 코드에서 오류 메시지가 발생하지 않도록 하려면 [\_\_declspec\(noreturn\)](../../cpp/noreturn.md)을 사용하여 `fatal`을 선언하십시오.