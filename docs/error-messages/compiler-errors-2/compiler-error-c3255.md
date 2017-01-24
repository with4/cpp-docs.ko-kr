---
title: "컴파일러 오류 C3255 | Microsoft Docs"
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
  - "C3255"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3255"
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3255
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'value type' : 이 값 형식 개체를 네이티브 힙에 동적으로 할당할 수 없습니다.  
  
 관리되는 멤버를 포함하는 값 형식\([Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md) 참조\)은 스택에는 만들 수 있지만 힙에는 만들 수 없습니다.  
  
 다음 샘플에서는 C3255 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3255.cpp  
// compile with: /clr  
using namespace System;  
value struct V {  
   Object^ o;  
};  
  
value struct V2 {  
   int i;  
};  
  
int main() {  
   V* pv = new V;   // C3255  
   V2* pv2 = new V2;  
   V v2;  
}  
```  
  
 **Managed Extensions for C\+\+**  
  
 다음 샘플에서는 C3255 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3255b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__value struct V {  
   Object* o;  
};  
  
__value struct V2 {  
   int i;  
};  
  
int main() {  
   V* pv = __nogc new V;   // C3255  
   V2* pv2 = __nogc new V2;   // OK  
}  
```