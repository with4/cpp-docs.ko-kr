---
title: "컴파일러 오류 C3768 | Microsoft Docs"
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
  - "C3768"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3768"
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3768
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

순수 관리 코드에서는 가상 vararg 함수의 주소를 가져올 수 없습니다.  
  
 `/clr:pure`를 사용하여 컴파일할 때는 가상 `vararg` 함수의 주소를 가져올 수 없습니다.  
  
 다음 샘플에서는 C3768 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3768.cpp  
// compile with: /clr:pure  
struct A  
{  
   virtual void f(...);  
};  
  
int main()  
{  
   &(A::f);   // C3768  
}  
```