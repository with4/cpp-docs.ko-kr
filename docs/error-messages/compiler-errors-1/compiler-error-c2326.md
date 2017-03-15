---
title: "컴파일러 오류 C2326 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2326"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2326"
ms.assetid: 01a5ea40-de83-4e6f-a4e8-469f441258e0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2326
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declarator': 함수에서 'name'에 액세스할 수 없습니다.  
  
 코드에서 멤버 변수를 수정하려고 하는데, 이는 불가능합니다.  
  
## 예제  
 다음 샘플에서는 C2326을 생성합니다.  
  
```  
// C2326.cpp void MyFunc() { int i; class MyClass  { public: void mf() { i = 4;   // C2326 i is inaccessible } }; }  
```