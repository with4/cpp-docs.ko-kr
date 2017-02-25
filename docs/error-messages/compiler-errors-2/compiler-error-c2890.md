---
title: "컴파일러 오류 C2890 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2890"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2890"
ms.assetid: 49147375-182c-42b1-b170-f475cd436d47
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2890
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : ref class은\(는\) 비인터페이스 기본 클래스를 하나만 사용할 수 있습니다.  
  
 참조 클래스 하나에는 기본 클래스가 하나만 있을 수 있습니다.  
  
 다음 샘플에서는 C2890 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2890.cpp  
// compile with: /clr /c  
ref class A {};  
ref class B {};  
ref class C : public A, public B {};   // C2890  
ref class D : public A {};   // OK  
```  
  
 **Managed Extensions for C\+\+**  
  
 다음 샘플에서는 C2890 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2890b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class A {};  
__gc class B {};  
  
__gc class C : public A, public B {};   // C2890  
__gc class D : public A {};   // OK  
```