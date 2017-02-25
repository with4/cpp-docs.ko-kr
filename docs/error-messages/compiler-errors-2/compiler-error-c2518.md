---
title: "컴파일러 오류 C2518 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2518"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2518"
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2518
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword' 키워드는 기본 클래스 목록에 사용할 수 없으므로 무시됩니다.  
  
 `class` 및 `struct` 키워드는 기본 클래스 목록에 있으면 안 됩니다.  
  
 다음 샘플에서는 C2518 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2518.cpp  
// compile with: /c  
class B {};  
class C : public class B {};   // C2518  
class D: public B {};   // OK  
```