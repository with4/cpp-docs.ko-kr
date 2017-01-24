---
title: "심각한 오류 C1045 | Microsoft Docs"
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
  - "C1045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1045"
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 한계 : 링크 사양이 너무 많이 중첩되었습니다.  
  
 중첩된 외부 참조가 컴파일러 한계를 초과했습니다. 중첩된 외부 참조는 `extern` "C\+\+"와 같은 외부 링크 형식에서 사용할 수 있습니다. 오류를 해결하려면 중첩된 외부 참조 수를 줄입니다.