---
title: 컴파일러 오류 C2574 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2574
dev_langs:
- C++
helpviewer_keywords:
- C2574
ms.assetid: 3e1c5c18-ee8b-4dbb-bfc0-d3b8991af71b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2832800f85e390c65d225671db9691b4bc13a6f3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2574"></a>컴파일러 오류 C2574
'소멸자': 정적으로 선언할 수 없습니다.  
  
 생성자 나 소멸자를 선언할 수 있습니다 `static`합니다.  
  
 다음 샘플에서는 C2574 오류가 생성 됩니다.  
  
```  
// C2574.cpp  
// compile with: /c  
class A {  
   virtual static ~A();   // C2574  
   //  try the following line instead  
   // virtual ~A();  
};  
```