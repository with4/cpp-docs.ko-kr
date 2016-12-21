---
title: "컴파일러 오류 C3891 | Microsoft Docs"
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
  - "C3891"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3891"
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3891
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 리터럴 데이터 멤버는 왼쪽 항의 값\(l\-value\)으로 사용할 수 없습니다.  
  
 [리터럴](../../windows/literal-cpp-component-extensions.md) 변수는 const이며 이 변수의 값은 선언에서 초기화한 후 변경할 수 없습니다.  
  
 다음 샘플에서는 C3891 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3891.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   Y1::staticConst = 0;   // C3891  
}  
```