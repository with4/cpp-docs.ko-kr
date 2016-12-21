---
title: "컴파일러 오류 C3192 | Microsoft Docs"
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
  - "C3192"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3192"
ms.assetid: 8b0083d4-706f-46f6-858a-e1d9af464cf8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3192
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 오류 : '^'는 전위 연산자가 아닙니다. '\*'를 잘못 사용한 것은 아닌지 확인하십시오.  
  
 핸들은 역참조 연산자로 사용할 수 없습니다.  
  
 다음 샘플에서는 C3192 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3192.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
public:  
   MyClass () {}  
   MyClass(MyClass%) {}  
};  
  
int main() {  
   MyClass ^ s = gcnew MyClass;   
   MyClass b = ^s;   // C3192  
  
   // OK  
   MyClass b2 = *s;  
}  
```