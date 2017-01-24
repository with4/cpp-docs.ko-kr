---
title: "컴파일러 오류 C2834 | Microsoft Docs"
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
  - "C2834"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2834"
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2834
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator'은\(는\) 전역으로 한정되어야 합니다.  
  
 `new` 및 `delete` 연산자는 상주하고 있는 클래스와 관련되어 있습니다.  범위 결정을 사용하여 여러 클래스에서 `new` 또는 `delete`의 버전을 선택할 수는 없습니다.  여러 형식의 `new` 또는 `delete` 연산자를 구현하려면 추가 형식 매개 변수를 사용하여 연산자의 버전을 만드십시오.