---
title: "컴파일러 경고 (수준 4) C4295 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4295"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4295"
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 경고 (수준 4) C4295
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**'**   
 ***array* ' : 배열이 너무 작아서 null 종결 문자를 포함할 수 없습니다.**  
  
 배열이 초기화되었지만 배열의 마지막 문자가 null이 아닙니다. 이 배열에 액세스하면 예기치 않은 결과가 발생합니다.  
  
 다음 샘플에서는 C4295 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4295.c  
// compile with: /W4  
  
int main() {  
   char a[3] = "abc";   // C4295  
}  
```