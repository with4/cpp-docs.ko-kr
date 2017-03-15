---
title: "컴파일러 오류 C3176 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3176"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3176"
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3176
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 지역 값 형식을 선언할 수 없습니다.  
  
 클래스는 전역 범위에서 값 형식으로만 선언할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 C3176 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3176.cpp  
// compile with: /clr  
int main () {  
   enum class C {};   // C3176  
}  
```