---
title: "컴파일러 경고 (수준 1) C4003 | Microsoft Docs"
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
  - "C4003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4003"
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' 매크로의 실제 매개 변수가 부족합니다.  
  
 매크로 정의의 형식 매개 변수 개수가 매크로의 실제 매개 변수 개수를 초과합니다.  매크로 확장에서는 누락된 매개 변수가 빈 텍스트로 대체됩니다.  
  
 다음 샘플에서는 C4003 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4003.cpp  
// compile with: /WX  
#define test(a,b) (a+b)  
  
int main()  
{  
   int a = 1;  
   int b = 2;  
   a = test(b);   // C4003  
   // try..  
   a = test(a,b);  
}  
```