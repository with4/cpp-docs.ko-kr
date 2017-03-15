---
title: "EXTERNDEF | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EXTERNDEF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EXTERNDEF directive"
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# EXTERNDEF
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

하나 이상의 외부 변수, 레이블 또는 호출 된 기호를 정의  *이름* 는 `type`.  
  
## 구문  
  
```  
  
EXTERNDEF [[langtype]] name:type [[, [[langtype]] name:type]]...  
```  
  
## 설명  
 경우  *이름* 정의 된 모듈을 것으로 처리 됩니다  [PUBLIC](../../assembler/masm/public-masm.md).  경우  *이름* 참조 하는 모듈에서 해당으로 처리 됩니다  [EXTERN](../../assembler/masm/extern-masm.md).  경우  *이름* 입니다 참조 않은 무시 됩니다.  `type` 수 있습니다  [ABS](../../assembler/masm/operator-abs.md), imports  *이름* 상수는.  일반적으로 사용 되는 파일에 포함 됩니다.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)