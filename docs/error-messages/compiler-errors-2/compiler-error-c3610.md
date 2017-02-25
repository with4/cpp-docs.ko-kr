---
title: "컴파일러 오류 C3610 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3610"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3610"
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3610
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'valuetype': 'method' 메서드를 호출하려면 값 형식이 'boxed'여야 합니다.  
  
 기본적으로 값 형식은 관리되는 힙에 없습니다.  `Object`를 비롯한 .NET 런타임 클래스의 메서드를 호출하려면 우선 값 형식을 관리되는 힙으로 이동해야 합니다.  
  
 C3610은 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C3610 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3610.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__value class A {};  
  
int main() {  
   A a;  
   a.GetType(); // C3610  
  
   // OK  
   __box A* ovar = __box(a);  
   ovar->GetType();  
}  
```