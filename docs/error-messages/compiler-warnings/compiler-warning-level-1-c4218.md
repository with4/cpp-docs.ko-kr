---
title: "컴파일러 경고 (수준 1) C4218 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4218"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4218"
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4218
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : 저장소 클래스 또는 형식을 적어도 하나는 지정해야 합니다.  
  
 기본 Microsoft 확장 \(\/Ze\)을 사용하면 형식이나 저장소 클래스를 지정하지 않고도 변수를 선언할 수 있습니다.  기본 형식은 `int`입니다.  
  
## 예제  
  
```  
// C4218.c  
// compile with: /W4  
i;  // C4218  
  
int main()  
{  
}  
```  
  
 이러한 선언은 ANSI 규격 \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 사용할 수 없습니다.