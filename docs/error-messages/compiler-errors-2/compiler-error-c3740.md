---
title: "컴파일러 오류 C3740 | Microsoft Docs"
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
  - "C3740"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3740"
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3740
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

템플릿이 이벤트의 소스가 되거나 이벤트를 받을 수 없습니다.  
  
 템플릿 기반 클래스 또는 구조체에 [event](../../cpp/event-handling.md)를 포함시킬 수 없습니다.  
  
 다음 샘플에서는 C3740 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3740.cpp  
template <typename T>   // Delete the template specification  
struct E {  
   __event void f();   // C3740  
};  
  
int main() {  
}  
```