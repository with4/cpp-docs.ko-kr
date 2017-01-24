---
title: "컴파일러 오류 C2627 | Microsoft Docs"
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
  - "C2627"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2627"
ms.assetid: 7fc6c5ac-c7c9-4f0b-ad52-f52252526458
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2627
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 명명되지 않은 공용 구조체에는 멤버 함수를 사용할 수 없습니다.  
  
 [익명 공용 구조체](../../misc/anonymous-unions.md)는 멤버 함수를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2627 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2627.cpp  
int main() {  
   union { void f(){} };   // C2627  
   union X { void f(){} };  
}  
```