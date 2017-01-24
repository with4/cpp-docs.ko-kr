---
title: "컴파일러 경고 (수준 1) C4399 | Microsoft Docs"
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
  - "C4399"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4399"
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4399
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : \/clr:pure로 컴파일한 경우 프로세스별 기호를 \_\_declspec\(dllimport\)로 표시할 수 없습니다.  
  
 네이티브 이미지 또는 네이티브 및 CLR 구문이 포함된 이미지의 데이터는 순수 이미지로 가져올 수 없습니다.  이 경고를 해결하려면 **\/clr:pure**가 아닌 **\/clr**로 컴파일하거나 `__declspec(dllimport)`을 삭제하십시오.  
  
## 예제  
 다음 샘플에서는 C4399 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```