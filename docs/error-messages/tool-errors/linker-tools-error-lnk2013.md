---
title: "링커 도구 오류 LNK2013 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2013"
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 링커 도구 오류 LNK2013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fixup type 픽스업 오버플로.대상 'symbol name'이\(가\) 범위를 벗어났습니다.  
  
 대상 기호가 명령 위치에서 너무 멀리 떨어져 있으므로 필요한 주소 또는 오프셋을 지정된 명령에 맞출 수 없습니다.  
  
 이미지를 여러 개 만들고 [\/ORDER](../../build/reference/order-put-functions-in-order.md) 옵션을 사용하여 명령과 대상을 좀 더 근접시킴으로써 이 문제를 해결할 수 있습니다.  
  
 기호 이름이 컴파일러에서 생성한 기호가 아닌 사용자 정의 기호인 경우 이 오류를 해결하기 위해 다음 작업을 시도해 볼 수 있습니다.  
  
-   정적 함수를 비정적 함수로 변경합니다.  
  
-   정적 함수를 포함하는 코드 섹션의 이름을 호출자 이름과 동일하게 바꿉니다.  
  
 `DUMPBIN /SYMBOLS`를 사용하여 함수가 정적인지 여부를 확인하십시오.