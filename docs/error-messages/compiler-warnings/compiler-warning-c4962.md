---
title: "컴파일러 경고 C4962 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4962"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4962"
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 경고 C4962
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 최적화를 하면 프로필 데이터가 일관성이 없어지므로 프로필 기반 최적화를 사용하지 않습니다.  
  
 함수의 개수\(프로필\) 데이터를 신뢰할 수 없기 때문에 함수가 \/LTCG:PGO로 컴파일되지 않았습니다. 해당 함수에 대한 신뢰할 수 없는 프로필 데이터가 포함된 .pgc 파일을 다시 생성하려면 프로파일링을 다시 실행합니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.