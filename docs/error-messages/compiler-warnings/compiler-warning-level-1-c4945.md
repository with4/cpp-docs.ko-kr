---
title: 컴파일러 경고 (수준 1) C4945 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4945
dev_langs:
- C++
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8218c0ce387f70cb13a4074a3b3d008a72b1fe3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4945"></a>컴파일러 경고(수준 1) C4945
'symbol': 'assembly2'에서 기호를 가져올 수 없습니다: 'assembly1' 다른 어셈블리에서 'symbol' 이미 가져왔기 대로  
  
 기호 참조 된 어셈블리에서 가져왔지만 해당 기호가 다른 참조 된 어셈블리에서 이미 가져왔습니다. 두 어셈블리 중 하나를 참조 하지 않거나 기호 이름을 어셈블리 중 하나에서 변경 합니다.  
  
 다음 샘플에서는 c4945 합니다.  
  
```  
// C4945a.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 그런 다음  
  
```  
// C4945b.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 그런 다음  
  
```  
// C4945c.cpp  
// compile with: /clr /LD /W1  
#using "C4945a.dll"  
#using "C4945b.dll"   // C4945  
```