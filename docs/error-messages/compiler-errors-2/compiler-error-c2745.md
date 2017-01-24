---
title: "컴파일러 오류 C2745 | Microsoft Docs"
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
  - "C2745"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2745"
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2745
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'token': 이 토큰을 식별자로 변환할 수 없습니다.  
  
 식별자는 올바른 문자로 구성되어야 합니다.  
  
 다음 샘플에서는 C2745 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2745.cpp  
// compile with: /clr  
int main() {  
   int __identifier([));   // C2745  
}  
```