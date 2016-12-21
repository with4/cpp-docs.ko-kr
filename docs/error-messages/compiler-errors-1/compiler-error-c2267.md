---
title: "컴파일러 오류 C2267 | Microsoft Docs"
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
  - "C2267"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2267"
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2267
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 블록 범위에 정적 함수를 사용할 수 없습니다.  
  
 지역 함수가 `static`으로 선언되었습니다.  정적 함수는 전역 범위를 사용해야 합니다.  
  
 다음 샘플에서는 C2267 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2267.cpp  
static int func2();   // OK  
int main() {  
    static int func1();   // C2267  
}  
```