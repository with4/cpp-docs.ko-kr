---
title: "컴파일러 오류 C2196 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2196"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2196"
ms.assetid: fd2f6a58-48ce-4e58-96f8-e37720feb8e7
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2196
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

case 값 'value'를 이미 사용했습니다.  
  
 switch 문에서 동일한 case 값을 두 번 이상 사용합니다.  
  
 다음 샘플에서는 C2196을 생성합니다.  
  
```  
// C2196.cpp int main() { int i = 0; switch( i ) { case 0: break; case 0:   // C2196 // try the following line instead // case 1: break; } }  
```