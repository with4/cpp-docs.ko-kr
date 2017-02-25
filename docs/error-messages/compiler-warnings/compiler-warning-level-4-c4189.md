---
title: "컴파일러 경고(수준 4) C4189 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4189"
ms.assetid: 7ad9242c-228e-4054-8244-5e914b618ef3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고(수준 4) C4189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 지역 변수가 초기화되었으나 참조되지 않았습니다.  
  
 변수가 선언 및 초기화되었지만 사용되지 않습니다.  
  
 다음 샘플에서는 C4189를 생성합니다.  
  
```  
// C4189.cpp // compile with: /W4 int main() { int a = 1;   // C4189, remove declaration to resolve }  
```