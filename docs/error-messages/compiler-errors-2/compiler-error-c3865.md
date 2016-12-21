---
title: "컴파일러 오류 C3865 | Microsoft Docs"
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
  - "C3865"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3865"
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3865
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'calling\_convention' : 네이티브 멤버 함수에만 사용할 수 있습니다.  
  
 전역 함수 또는 관리되는 멤버 함수에 호출 규칙이 사용되었습니다.  호출 규칙은 관리되는 멤버 함수가 아닌 네이티브 멤버 함수에만 사용할 수 있습니다.  
  
 자세한 내용은 [호출 규칙](../../cpp/calling-conventions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3865 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3865.cpp  
// compile with: /clr  
// processor: x86  
void __thiscall Func(){}   // C3865  
  
// OK  
struct MyType {  
   void __thiscall Func(){}  
};  
```