---
title: "컴파일러 오류 C3892 | Microsoft Docs"
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
  - "C3892"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3892"
ms.assetid: 83fff42c-ea48-442f-bc2e-b33a6b99d890
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3892
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : const인 변수에 할당할 수 없습니다.  
  
 const 변수는 선언하고 초기화한 이후에는 변경할 수 없습니다.  
  
 다음 샘플에서는 C3892 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3892.cpp  
// compile with: /clr  
ref struct Y1 {  
   static const int staticConst = 9;  
};  
  
int main() {  
   Y1::staticConst = 0;   // C3892  
}  
```