---
title: "컴파일러 오류 C3737 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3737"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3737"
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3737
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'delegate': 대리자에서 명시적 호출 규칙을 사용하지 않은 것 같습니다.  
  
 [\_\_delegate](../../misc/delegate.md)에 [호출 규칙](../../cpp/calling-conventions.md)을 지정할 수 없습니다.  
  
 다음 샘플에서는 C3737 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3737a.cpp  
// compile with: /clr  
delegate void __stdcall MyFunc();   // C3737  
// Try the following line instead.  
// delegate void MyFunc();  
  
int main() {  
}  
```  
  
 다음 샘플에서는 C3737 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3737b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__delegate void __stdcall MyFunc();   // C3737  
// Try the following line instead.  
// __delegate void MyFunc();  
  
int main() {  
}  
```