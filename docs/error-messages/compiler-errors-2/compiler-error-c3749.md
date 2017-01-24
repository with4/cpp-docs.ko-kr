---
title: "컴파일러 오류 C3749 | Microsoft Docs"
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
  - "C3749"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3749"
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3749
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute': 사용자 지정 특성은 함수 안에서 사용될 수 없습니다.  
  
 사용자 지정 특성은 함수 안에서 사용될 수 없습니다. 사용자 지정 특성에 대한 자세한 내용은 [attribute](../../windows/attribute.md) 항목을 참조하십시오.  
  
 다음 샘플에서는 C3749 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3749a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
public ref struct ABC : public Attribute {  
   ABC() {}  
};  
  
void f1() { [ABC]; };  // C3749  
```  
  
 다음 샘플에서는 C3749 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3749b.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
  
[attribute(All)]  
public __gc struct ABC {  
   ABC() {}  
};  
  
void f1() { [ABC]; };  // C3749  
```