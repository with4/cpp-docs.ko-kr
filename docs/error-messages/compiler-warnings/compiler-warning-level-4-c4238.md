---
title: 컴파일러 경고 (수준 4) C4238 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4238
dev_langs:
- C++
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06dbec01da8d1b47cb7b93c90a22ae5266e9b4c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292440"
---
# <a name="compiler-warning-level-4-c4238"></a>컴파일러 경고(수준 4) C4238
비표준 확장이 사용 됨: 클래스 rvalue를 lvalue로 사용  
  
 Visual c + +, Microsoft 확장의 이전 버전과 호환성에 대 한 (**/Ze**) 컨텍스트에서 rvalue를 암시적 또는 명시적으로 해당 주소를 사용 하는 대로 클래스 형식을 사용할 수 있습니다. 다음 예제와 같은 일부 경우가 위험할 수 있습니다.  
  
## <a name="example"></a>예제  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 이러한 사용은 ANSI 규격 오류 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).