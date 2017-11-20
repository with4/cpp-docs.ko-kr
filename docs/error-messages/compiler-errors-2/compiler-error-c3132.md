---
title: "컴파일러 오류 C3132 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3132
dev_langs: C++
helpviewer_keywords: C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4922c6095381b42c0b01052421e19f841932be5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3132"></a>컴파일러 오류 C3132
' 함수 매개 변수 ': 매개 변수 배열 '관리 되는 1 차원 배열' 형식의 형식 인수에만 적용 될 수 있습니다  
  
 [ParamArray](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx) 특성이 1 차원 배열 되지 않은 매개 변수에 적용 되었습니다.  
  
 다음 샘플에서는 C3132 오류가 생성 됩니다.  
  
```  
// C3132.cpp  
// compile with: /clr /c  
using namespace System;  
void f( [ParamArray] Int32[,] );   // C3132  
void g( [ParamArray] Int32[] );   // C3132  
  
void h( [ParamArray] array<Char ^> ^ MyArray );   // OK  
  
```