---
title: "컴파일러 오류 C2273 | Microsoft Docs"
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
  - "C2273"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2273"
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2273
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': '.''\-\>' 연산자의 오른쪽에 사용할 수 없습니다.  
  
 형식이 `->` 연산자의 오른쪽 피연산자로 표시됩니다.  
  
 사용자 정의 형식 변환에 액세스하려고 하는 경우 이 오류가 발생할 수 있습니다.  \>와 `type` 사이에 `operator` 키워드를 사용하십시오.  
  
 다음 샘플에서는 C2273 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2273.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
int main() {  
   MyClass * ClassPtr = new MyClass;  
   int i = ClassPtr->int();   // C2273  
   int j = ClassPtr-> operator int();   // OK  
}  
```