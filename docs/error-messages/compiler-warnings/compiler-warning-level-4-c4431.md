---
title: "컴파일러 경고 (수준 4) C4431 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4431"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4431"
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 경고 (수준 4) C4431
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 지정자가 없습니다. int로 가정합니다.참고: C에서는 더 이상 기본 int를 지원하지 않습니다.  
  
 이 오류는 Visual C\+\+ 2005에 대해 적용되었으며, Visual C\+\+에서 더 이상 형식화되지 않은 식별자를 기본적으로 int로 만들지 않는다는 컴파일러 규칙의 결과로 발생할 수 있습니다.  식별자의 형식을 명시적으로 지정해야 합니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4431 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4431.c  
// compile with: /c /W4  
#pragma warning(default:4431)  
i;   // C4431  
int i;   // OK  
```