---
title: "컴파일러 경고 (수준 3) C4619 | Microsoft Docs"
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
  - "C4619"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4619"
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4619
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma warning : 경고 번호 'number'이\(가\) 없습니다.  
  
 존재하지 않는 경고를 비활성화하려고 했습니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 다음 샘플에서는 C4619 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4619.cpp  
// compile with: /W3 /c  
#pragma warning(default : 4619)  
#pragma warning(disable : 4354)   // C4619, C4354 does not exist  
```