---
title: "컴파일러 오류 C2109 | Microsoft Docs"
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
  - "C2109"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2109"
ms.assetid: 2d1ac79d-a985-4904-a38b-b270578d664d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2109
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

첨자는 배열 또는 포인터 형식을 사용해야 합니다.  
  
 첨자가 배열이 아닌 변수에 사용되었습니다.  
  
 다음 샘플에서는 C2109 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2109.cpp  
int main() {  
   int a, b[10] = {0};  
   a[0] = 1;   // C2109  
   b[0] = 1;   // OK  
}  
```