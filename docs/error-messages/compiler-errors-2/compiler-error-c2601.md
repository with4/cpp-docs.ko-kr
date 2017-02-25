---
title: "컴파일러 오류 C2601 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2601"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2601"
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2601
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수를 로컬로 정의하면 안 됩니다.  
  
 코드가 함수 내에서 함수를 정의하려고 합니다.  
  
 또는 소스 코드에서 C2601 오류 위치 앞쪽에 짝이 맞지 않는 중괄호가 있습니다.  
  
 다음 샘플에서는 C2601 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2601.cpp  
int main() {  
   int i = 0;  
  
   void funcname(int j) {   // C2601  
      j++;  
   }  
}  
```