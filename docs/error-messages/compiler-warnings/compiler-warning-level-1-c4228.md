---
title: "컴파일러 경고 (수준 1) C4228 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4228"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4228"
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4228
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : 선언자 목록에서 쉼표 뒤의 한정자가 무시됩니다.  
  
 변수를 선언할 때 **const** 또는 `volatile`과 같은 한정자를 쉼표 뒤에 사용하는 것은 Microsoft 확장\([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\)에 속합니다.  
  
## 예제  
  
```  
// C4228.cpp  
// compile with: /W1  
int j, const i = 0;  // C4228  
int k;  
int const m = 0;  // ok  
int main()  
{  
}  
```