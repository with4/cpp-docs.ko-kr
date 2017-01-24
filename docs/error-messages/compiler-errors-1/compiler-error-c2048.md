---
title: "컴파일러 오류 C2048 | Microsoft Docs"
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
  - "C2048"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2048"
ms.assetid: 44704726-85fc-42f0-afb9-194df8c4ca7c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2048
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본값이 둘 이상입니다.  
  
 `switch` 문에 `default` 레이블이 여러 개 포함되어 있습니다. 오류를 해결하려면 `default` 레이블 중 하나를 삭제합니다.  
  
 다음 샘플에서는 C2048을 생성합니다.  
  
```  
// C2048.cpp int main() { int a = 1; switch (a) { case 1: a = 0; default: a = 2; default:   // C2048 a = 3; } }  
```  
  
 해결 방법:  
  
```  
// C2048b.cpp int main() { int a = 1; switch (a) { case 1: a = 0; default: a = 2; } }  
```