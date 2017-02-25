---
title: "컴파일러 경고(수준 4) C4057 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4057"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4057"
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고(수준 4) C4057
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': 'identifier1'은 약간 다른 기본 형식에 대한 간접 참조가 'identifier2'와 다릅니다.  
  
 두 포인터 식은 다른 기본 형식을 참조합니다. 식을 변환하지 않고 사용합니다.  
  
### 다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  부호 있는 형식과 부호 없는 형식을 혼합합니다.  
  
2.  **short** 및 **long** 형식을 혼합합니다.