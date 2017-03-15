---
title: "컴파일러 오류 C3360 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3360"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3360"
ms.assetid: 6acf983a-dbb6-422b-b045-a34bb4ba6761
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3360
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'string': 이름을 만들 수 없습니다.  
  
 [uuid](../../windows/uuid-cpp-attributes.md) 특성에 전달된 값이 잘못되었습니다.  
  
 다음 샘플에서는 C3360을 생성합니다.  
  
```  
// C3360.cpp [ uuid("1") ] // try this line instead // [ uuid("12341234-1234-1234-1234-123412341234") ] struct A   // C3360 { }; int main() { }  
```