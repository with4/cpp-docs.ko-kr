---
title: "컴파일러 오류 C2050 | Microsoft Docs"
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
  - "C2050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2050"
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

switch 식이 정수 계열이 아닙니다.  
  
 `switch` 식은 비정수 값으로 계산됩니다.  이 오류를 해결하려면 switch 문에 정수 계열 값만 사용하십시오.  
  
 다음 샘플에서는 C2050 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2050.cpp  
int main() {  
   int a = 1;  
   switch ("a") {   // C2050  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
   }  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2050b.cpp  
int main() {  
   int a = 1;  
   switch (a) {  
      case 1:  
         a = 0;  
      default:  
         a = 2;  
   }  
}  
```