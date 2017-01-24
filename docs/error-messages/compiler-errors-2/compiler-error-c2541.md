---
title: "컴파일러 오류 C2541 | Microsoft Docs"
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
  - "C2541"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2541"
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2541
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'delete': delete: 포인터가 아닌 개체를 삭제할 수 없습니다.  
  
 [delete](../../cpp/delete-operator-cpp.md) 연산자가 포인터가 아닌 개체에 사용되었습니다.  
  
 다음 샘플에서는 C2541 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2541.cpp  
int main() {  
   int i;  
   delete i;   // C2541 i not a pointer  
  
   // OK  
   int *ip = new int;  
   delete ip;  
}  
```