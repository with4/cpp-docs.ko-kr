---
title: "컴파일러 경고 (수준 1) C4144 | Microsoft Docs"
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
  - "C4144"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4144"
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4144
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'expression' : 관계식을 switch 식으로 사용했습니다.  
  
 지정된 관계식이 [switch](../../cpp/switch-statement-cpp.md) 문의 제어식으로 사용되었습니다.  관련된 case 문에 부울 값이 제공됩니다.  다음 샘플에서는 C4144 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4144.cpp  
// compile with: /W1  
int main()  
{  
   int i = 0;  
   switch(!i) {   // C4144, remove the ! to resolve  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```