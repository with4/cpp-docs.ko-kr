---
title: "컴파일러 오류 C3623 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3623"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3623"
ms.assetid: a0341b45-062a-4f67-beb9-ba74201ed1ed
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3623
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable': 관리되는 형식 또는 WinRT 형식에서는 비트 필드가 지원되지 않습니다.  
  
 'variable': 관리되는 클래스 또는 WinRT 클래스의 변수에서는 비트 필드를 사용할 수 없습니다.  
  
 다음 샘플에서는 C3623 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3623.cpp  
// compile with: /clr  
using namespace System;  
ref class CMyClass {  
public:  
   int i : 1;   // C3623  
};  
  
int main() {  
   CMyClass^ pMyClass = gcnew CMyClass();  
   pMyClass->i = 3;  
   Console::Out->WriteLine(pMyClass->i);  
}  
```  
  
 다음 샘플에서는 C3623 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3623_2.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
__gc class CMyClass {  
   public:  
      int i : 1;   // C3623  
};  
  
int main() {  
   CMyClass *pMyClass = new CMyClass();  
   pMyClass->i = 3;  
   Console::Out->WriteLine(pMyClass->i);  
}  
```