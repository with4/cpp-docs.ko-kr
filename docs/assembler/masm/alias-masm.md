---
title: "ALIAS (MASM) | Microsoft Docs"
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
  - "Alias"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALIAS directive"
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ALIAS (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

해당  **별칭** 지시문의 함수에 대 한 대체 이름을 만듭니다.  함수에 여러 개의 이름 또는 링커 \(LINK.exe\) 이전에 함수의 새 함수에 매핑할 수 있도록 라이브러리를 만들 수 있습니다.  
  
## 구문  
  
```  
  
ALIAS  <  
alias  
> = <  
actual-name  
>  
  
```  
  
#### 매개 변수  
 `actual-name`  
 함수 또는 프로시저의 실제 이름입니다.  꺾쇠 괄호는 필수입니다.  
  
 `alias`  
 대체 또는 별칭 이름입니다.  꺾쇠 괄호는 필수입니다.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)