---
title: "컴파일러 오류 C2270 | Microsoft Docs"
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
  - "C2270"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2270"
ms.assetid: b52c068e-0b61-42e7-b775-4d57b3ddcba0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2270
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 비멤버 함수에 한정자를 사용할 수 없습니다.  
  
 비멤버 함수가 [const](../../cpp/const-cpp.md), [volatile](../../cpp/volatile-cpp.md) 또는 별개의 메모리 모델 한정자를 사용하여 선언되었습니다.  
  
 다음 샘플에서는 C2270 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2270.cpp  
// compile with: /c  
void func1(void) const;   // C2270, nonmember function  
  
void func2(void);  
  
class CMyClass {  
public:  
   void func2(void) const;  
};  
```