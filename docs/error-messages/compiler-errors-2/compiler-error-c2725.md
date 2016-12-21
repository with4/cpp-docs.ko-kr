---
title: "컴파일러 오류 C2725 | Microsoft Docs"
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
  - "C2725"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2725"
ms.assetid: 13cd5b1b-e906-4cd8-9b2b-510d587c665a
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2725
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'exception': 관리되는 또는 WinRT 개체를 값이나 참조로 throw 또는 catch할 수 없습니다.  
  
 관리되는 또는 WinRT 예외의 형식이 올바르지 않습니다.  
  
## 예제  
 다음 샘플에서는 C2725를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2725.cpp  
// compile with: /clr  
ref class R {  
public:  
   int i;  
};  
  
int main() {  
   R % r1 = *gcnew R;  
   throw r1;   // C2725  
  
   R ^ r2 = gcnew R;  
   throw r2;   // OK     
}  
```  
  
## 예제  
 다음 샘플에서는 C2725를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2725b.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   try {}  
   catch( System::Exception%) {}   // C2725  
   // try the following line instead  
   // catch( System::Exception ^e) {}  
}  
```  
  
## 예제  
 다음 샘플에서는 C2725를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2725c.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
int main() {  
   try {}  
   catch( System::Exception&) {}   // C2725  
   // try the following line instead  
   // catch( System::Exception *e) {}  
}  
```