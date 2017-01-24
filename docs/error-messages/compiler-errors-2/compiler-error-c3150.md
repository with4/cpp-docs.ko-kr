---
title: "컴파일러 오류 C3150 | Microsoft Docs"
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
  - "C3150"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3150"
ms.assetid: c1ff28f5-52fe-4fd4-81d0-2e0ad8548631
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3150
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'element' : 'attribute'은\(는\) 클래스, 인터페이스, 배열 또는 포인터에만 적용될 수 있습니다.  
  
 [\_\_gc](../../misc/gc.md)는 클래스, 인터페이스 또는 배열에서만 사용할 수 있습니다.  
  
 C3150은 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C3150 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3150.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc void f()   // C3150; function cannot be managed  
{  
}  
```