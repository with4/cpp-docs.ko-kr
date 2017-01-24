---
title: "컴파일러 오류 C3132 | Microsoft Docs"
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
  - "C3132"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3132"
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3132
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function\-parameter' : 매개 변수 배열은 '단일 차원의 관리되는 배열' 형식의 형식 인수에만 적용할 수 있습니다.  
  
 [ParamArray](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx) 특성을 단일 차원 배열이 아닌 매개 변수에 적용했습니다.  
  
 다음 샘플에서는 C3132 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3132.cpp  
// compile with: /clr /c  
using namespace System;  
void f( [ParamArray] Int32[,] );   // C3132  
void g( [ParamArray] Int32[] );   // C3132  
  
void h( [ParamArray] array<Char ^> ^ MyArray );   // OK  
  
```