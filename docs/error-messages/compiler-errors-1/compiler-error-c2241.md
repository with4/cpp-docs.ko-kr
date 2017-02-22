---
title: "컴파일러 오류 C2241 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2241"
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C2241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 멤버 액세스가 제한됩니다.  
  
 코드가 전용 또는 보호된 멤버에 액세스하려고 합니다.  
  
### 다음 해결 방법을 사용하여 수정하려면  
  
1.  멤버의 액세스 수준을 변경합니다.  
  
2.  멤버를 액세스하는 함수의 `friend`로 선언합니다.