---
title: "컴파일러 경고 (수준 1) C4545 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4545"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4545"
ms.assetid: 43f8f34f-ed46-4661-95c0-c588c577ff73
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4545
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

쉼표 앞의 식이 인수 목록이 없는 함수로 계산됩니다.  
  
 컴파일러에서 형식이 올바르지 않은 쉼표 식을 발견했습니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 다음 샘플에서는 C4545 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4545.cpp  
// compile with: /W1  
#pragma warning (default : 4545)  
  
void f() { }  
  
int main()  
{  
   *(&f), 10;   // C4545  
   // try the following line instead  
   // (*(&f))(), 10;  
}  
```