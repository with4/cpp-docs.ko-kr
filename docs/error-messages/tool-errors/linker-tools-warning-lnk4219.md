---
title: "링커 도구 경고 LNK4219 | Microsoft Docs"
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
  - "LNK4219"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4219"
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4219
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fixup name 픽스업 오버플로.대상 'target symbol name'이\(가\) 범위를 벗어났습니다. 썽크가 삽입됩니다.  
  
 대상 기호가 명령 위치에서 너무 멀리 떨어져 있으므로, 지정된 명령에 주소나 오프셋이 적합하지 않은 상황에서 링커가 썽크를 삽입했습니다.  
  
 이미지를 다시 정렬하여\(예: [\/ORDER](../../build/reference/order-put-functions-in-order.md) 옵션 사용\) 간접 참조의 추가 수준을 방지할 수 있습니다.