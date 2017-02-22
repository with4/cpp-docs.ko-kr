---
title: "컴파일러 오류 C3153 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3153"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3153"
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3153
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : 인터페이스의 인스턴스를 만들 수 없습니다.  
  
 인터페이스는 인스턴스화할 수 없습니다.  인터페이스 멤버를 사용하려면 인터페이스에서 클래스를 파생시키고 인터페이스 멤버를 구현한 다음 멤버를 사용하십시오.  
  
 다음 샘플에서는 C3153 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3153.cpp  
// compile with: /clr  
interface class A {  
};  
  
int main() {  
   A^ a = gcnew A;   // C3153  
}  
```  
  
 다음 샘플에서는 C3153 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3153b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__interface A {  
};  
  
int main() {  
   A *a = new A;   // C3153  
}  
```