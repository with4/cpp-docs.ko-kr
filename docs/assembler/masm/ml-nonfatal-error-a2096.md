---
title: "ML Nonfatal Error A2096 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2096"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2096"
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2096
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**세그먼트, 그룹 또는 세그먼트 레지스터가 필요 합니다.**  
  
 세그먼트 또는 그룹 필요 하지만 찾을 수 없습니다.  
  
 다음 중 하나가 발생 했습니다.  
  
-   세그먼트를 지정 된 왼쪽된 피연산자는 연산자 재정의 \(:**:**\) 세그먼트 레지스터 \(CS, DS, SS, ES, FS, 또는 GS\), 그룹 이름, 세그먼트 이름 또는 세그먼트 식이 아닙니다.  
  
-   해당  [가정](../../assembler/masm/assume.md) 지시문 세그먼트 레지스터가 올바른 세그먼트 주소, 세그먼트 레지스터, 그룹 또는 특수 하지 않고 지정 된  **플랫** 그룹.  
  
## 참고 항목  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)