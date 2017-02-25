---
title: "컴파일러 오류 C2563 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2563"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2563"
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2563
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 매개 변수 목록에 불일치가 있습니다.  
  
 함수\(또는 함수의 포인터\)의 형식 매개 변수 목록이 다른 함수\(또는 멤버 함수의 포인터\)의 형식 매개 변수 목록과 일치하지 않습니다.  따라서 함수 또는 포인터에 대한 할당을 수행할 수 없습니다.  
  
 다음 샘플에서는 C2563 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```