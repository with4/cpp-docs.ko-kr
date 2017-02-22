---
title: "컴파일러 오류 C3181 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3181"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3181"
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3181
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : operator에 대한 피연산자가 잘못되었습니다.  
  
 잘못된 매개 변수가 [\_\_typeof](../../misc/typeof.md) 또는 [typeid](../../windows/typeid-cpp-component-extensions.md) 연산자에 전달되었습니다.  매개 변수는 관리되는 형식이어야 합니다.  
  
 컴파일러는 공용 언어 런타임의 형식에 매핑되는 네이티브 형식의 별칭을 사용합니다.  
  
 다음 샘플에서는 C3181 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3181a.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181  
   Type ^pType2 = int::typeid;   // OK  
}  
```  
  
 다음 샘플에서는 C3181 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3181b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
int main() {  
   Type *pType1 = __typeof(int __gc*);   // C3181  
   Type *pType2 = __typeof(int*);   // OK  
}  
```