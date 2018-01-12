---
title: "컴파일러 오류 C2652 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2652
dev_langs: C++
helpviewer_keywords: C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b470511c6d9a654357d0c8007083a2d754e300ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2652"></a>컴파일러 오류 C2652
'identifier': 잘못 된 복사 생성자: 첫 번째 매개 변수에는 'identifier'를 사용 해야 합니다.  
  
 복사 생성자의 첫 번째 매개 변수는 동일한 클래스, 구조체 또는 공용 구조체 정의 된 형식을 있습니다. 첫 번째 매개 변수 형식이 있지만 형식 자체에 대 한 참조 수 있습니다.  
  
 다음 샘플에서는 C2651 오류가 생성 됩니다.  
  
```  
// C2652.cpp  
// compile with: /c  
class A {  
   A( A );   // C2652 takes an A  
};  
class B {  
   B( B& );   // OK, reference to B  
};  
```