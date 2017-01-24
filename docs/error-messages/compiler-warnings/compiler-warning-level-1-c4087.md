---
title: "컴파일러 경고(수준 1) C4087 | Microsoft Docs"
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
  - "C4087"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4087"
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4087
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 'void' 매개 변수 목록을 사용하여 선언되었습니다.  
  
 함수 선언에 정식 매개 변수가 없지만 함수 호출에 실제 매개 변수가 있습니다. 추가 매개 변수는 함수 호출 규칙에 따라 전달됩니다.  
  
 이 경고는 C 컴파일러용입니다.  
  
## 예제  
  
```  
// C4087.c // compile with: /W1 int f1( void ) { } int main() { f1( 10 );   // C4087 }  
```