---
title: "COMM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COMM"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMM directive"
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# COMM
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

있는지 변수에 지정 된 특성을 만듭니다 `definition`.  
  
## 구문  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## 설명  
 각 `definition` 형식은 다음과 같습니다.  
  
 \[*langtype*\]\] \[**NEAR** &#124; **FAR**\]*label***:**`type`\[**:***count*\]  
  
 해당  *레이블* 변수 이름입니다.  `type` 모든 형식 지정자를 사용할 수 있습니다 \([바이트](../../assembler/masm/byte-masm.md),  [단어](../../assembler/masm/word.md)등\) 또는 바이트 수를 지정 하는 정수입니다.  *수* 데이터 객체 \(하나는 기본값\)을 지정 합니다.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)