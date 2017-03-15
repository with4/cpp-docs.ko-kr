---
title: "컴파일러 오류 C2054 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2054"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2054"
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2054
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' 다음에 '\('가 필요합니다.  
  
 닫는 괄호가 필요한 컨텍스트에 함수 식별자가 사용되었습니다.  
  
 이 오류는 복잡한 초기화에서 등호\(\=\)가 누락된 경우에 발생할 수 있습니다.  
  
 다음 샘플에서는 C2054 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2054.c  
int array1[] { 1, 2, 3 };   // C2054, missing =  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2054b.c  
int main() {  
   int array2[] = { 1, 2, 3 };  
}  
```