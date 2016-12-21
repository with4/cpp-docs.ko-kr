---
title: "심각한 오류 C1047 | Microsoft Docs"
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
  - "C1047"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1047"
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1047
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

개체 또는 라이브러리 파일 'file'은 다른 개체에 사용한 컴파일러보다 이전 컴파일러로 만들어졌습니다. 해당 개체 및 라이브러리를 다시 빌드하세요.  
  
 **\/LTCG**로 빌드되는 개체 파일 또는 라이브러리가 함께 연결되었지만 해당 개체 파일 또는 라이브러리가 다른 버전의 Visual C\+\+ 도구 집합으로 빌드되는 경우 C1047이 발생합니다.  
  
 새 버전의 컴파일러를 사용하여 시작되지만 기존 개체 파일 또는 라이브러리를 완전히 다시 빌드하지 않는 경우 발생할 수 있습니다.  
  
 C1047을 해결하려면 모든 개체 파일 또는 라이브러리를 다시 빌드합니다.