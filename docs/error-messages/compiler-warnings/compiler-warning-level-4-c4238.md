---
title: "컴파일러 경고 (수준 4) C4238 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4238
dev_langs:
- C++
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e8e52868d97d31243f92307e9bfd158c818c2f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4238"></a>컴파일러 경고(수준 4) C4238
비표준 확장이 사용 됨: 클래스 rvalue를 lvalue로 사용  
  
 Visual c + +, Microsoft 확장의 이전 버전과 호환성에 대 한 (**/Ze**) 컨텍스트에서 rvalue를 암시적 또는 명시적으로 해당 주소를 사용 하는 대로 클래스 형식을 사용할 수 있습니다. 다음 예제와 같은 일부 경우가 위험할 수 있습니다.  
  
## <a name="example"></a>예  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 이러한 사용은 ANSI 규격 오류 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).