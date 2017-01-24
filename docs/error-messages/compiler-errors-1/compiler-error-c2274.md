---
title: "컴파일러 오류 C2274 | Microsoft Docs"
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
  - "C2274"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2274"
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2274
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': '.' 연산자의 오른쪽에 사용할 수 없습니다.  
  
 형식이 멤버 액세스 연산자\(.\)의 오른쪽 피연산자에 나타납니다.  
  
 사용자 정의 형식 변환에 액세스하려고 하는 경우 이 오류가 발생할 수 있습니다.  마침표와 `type` 사이에 `operator` 키워드를 사용하십시오.  
  
 다음 샘플에서는 C2286 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2274.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
  
int main() {  
   MyClass ClassName;  
   int i = ClassName.int();   // C2274  
   int j = ClassName.operator int();   // OK  
}  
```