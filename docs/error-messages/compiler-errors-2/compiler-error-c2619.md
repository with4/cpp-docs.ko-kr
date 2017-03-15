---
title: "컴파일러 오류 C2619 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2619"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2619"
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2619
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 익명 구조체 또는 집합체에는 정적 데이터 멤버가 허용되지 않습니다.  
  
 익명 구조체 또는 공용 구조체의 멤버는 `static`으로 선언됩니다.  
  
 다음 샘플에서는 C2619 오류가 발생하는 경우 및 static 키워드를 제거하여 오류를 해결하는 방법을 보여 줍니다.  
  
```  
// C2619.cpp  
int main() {  
   union { static int j; };  // C2619  
   union { int j; };  // OK  
}  
```