---
title: "컴파일러 오류 C3530 | Microsoft Docs"
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
  - "C3530"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3530"
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3530
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'auto'는 다른 형식 지정자와 함께 사용할 수 없습니다.  
  
 형식 지정자가 `auto`키워드와 함께 사용되었습니다.  
  
### 이 오류를 해결하려면  
  
1.  `auto` 키워드를 사용하는 변수 선언에서는 형식 지정자를 사용하지 마십시오.  
  
## 예제  
 다음 예제에서는 `x` 변수가 `auto` 키워드 및 `int` 형식과 함께 선언되고 이 예제가 **\/Zc:auto**로 컴파일되었기 때문에 C3530이 발생합니다.  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## 참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)