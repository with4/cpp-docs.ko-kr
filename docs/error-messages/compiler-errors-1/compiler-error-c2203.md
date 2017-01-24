---
title: "컴파일러 오류 C2203 | Microsoft Docs"
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
  - "C2203"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2203"
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2203
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

delete 연산자는 배열의 범위를 지정할 수 없습니다.  
  
 **\/Za**\(ANSI\) 옵션을 사용하면 `delete` 연산자가 전체 배열을 삭제할 수 있지만 배열의 일부나 특정 멤버를 삭제할 수는 없습니다.  
  
 다음 샘플에서는 C2203 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2203.cpp  
// compile with: /Za  
int main() {  
   int *ar = new int[10];  
   delete [4] ar;   // C2203  
   // try the following line instead  
   // delete [] ar;  
}  
```