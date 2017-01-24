---
title: "컴파일러 경고 (수준 4) C4032 | Microsoft Docs"
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
  - "C4032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4032"
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 매개 변수 'number'의 형식이 다릅니다.  
  
 매개 변수 형식은 기본 확장이긴 하지만 이전 선언에서의 형식과 호환되지 않습니다.  
  
 이는 ANSI C\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)의 오류이며 Microsoft 확장\(\/Ze\)에서의 경고 사항입니다.  
  
## 예제  
  
```  
// C4032.c  
// compile with: /W4  
void func();  
void func(char);   // C4032, char promotes to int  
  
int main()  
{  
}  
```