---
title: "컴파일러 오류 C3854 | Microsoft Docs"
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
  - "C3854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3854"
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\=' 왼쪽의 식이 함수로 평가됩니다.함수에 할당할 수 없습니다\(함수는 l\-값이 아님\).  
  
 참조를 다시 초기화할 수 없습니다.  함수에 대한 참조를 역참조하면 rvalue인 함수가 생성됩니다. 이는 함수에 할당할 수 없습니다.  따라서 함수에 대한 참조를 통해 할당할 수 없습니다.  
  
 다음 샘플에서는 C3854 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3854.cpp  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
typedef int (* pFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   pFunc_t pf = &afunc;   // OK initializing a pointer to function  
  
   *pf = &afunc;   // C3854  
   // try the following line instead  
   // pf = &afunc;  
   *rf = &afunc;   // C3854  
}  
```