---
title: "컴파일러 경고(수준 4) C4125 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4125"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4125"
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 4) C4125
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

10진수가 8진수 이스케이프 시퀀스를 마칩니다.  
  
 컴파일러가 10진수 없는 8진수를 계산하고 10진수를 문자로 가정합니다.  
  
## 예제  
  
```  
// C4125a.cpp // compile with: /W4 char array1[] = "\709"; // C4125 int main() { }  
```  
  
 숫자 9가 문자로 사용된 경우 예제를 다음과 같이 수정합니다.  
  
```  
// C4125b.cpp // compile with: /W4 char array[] = "\0709";  // C4125 String containing "89" int main() { }  
```