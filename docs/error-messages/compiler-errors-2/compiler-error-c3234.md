---
title: "컴파일러 오류 C3234 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3234"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3234"
ms.assetid: ebefc15a-e40d-424b-a3dd-d7e185d0ed7b
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3234
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

제네릭 클래스는 제네릭 형식 매개 변수에서 상속할 수 없습니다.  
  
 제네릭 클래스는 제네릭 형식 매개 변수에서 상속할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3234를 생성합니다.  
  
```  
// C3234.cpp // compile with: /clr /c generic <class T> public ref class C : T {};   // C3234 // try the following line instead // public ref class C {};  
```