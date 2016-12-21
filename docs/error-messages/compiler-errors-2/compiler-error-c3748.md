---
title: "컴파일러 오류 C3748 | Microsoft Docs"
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
  - "C3748"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3748"
ms.assetid: 6fe71a0a-dd93-4ce6-9729-b9616360cf34
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3748
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface': 관리되지 않는 인터페이스는 이벤트를 발생시킬 수 없습니다.  
  
 [\_\_event](../../cpp/event.md) 키워드를 인터페이스 내부에 표시할 수 없습니다.  
  
 다음 샘플에서는 C3748 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3748.cpp  
__interface I {  
// try the following line instead  
// struct I {  
   __event void f();   // C3748  
};  
  
int main() {  
}  
```