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
ms.openlocfilehash: 56cfdf52ec3a6947a6a82774f551fc1a6880c959
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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