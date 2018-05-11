---
title: 컴파일러 경고 (수준 1) C4624 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4624
dev_langs:
- C++
helpviewer_keywords:
- C4624
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d11bc5c8b5034fa305a22ba893c62faff18cc38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4624"></a>컴파일러 경고(수준 1) C4624
'derived class': 기본 클래스의 소멸자에 액세스할 수 없거나 이러한 소멸자가 삭제되므로 소멸자가 암시적으로 삭제된 것으로 정의됩니다.  
  
 기본 클래스에서 소멸자에 액세스할 수 없거나 소멸자가 삭제되었으므로 파생 클래스에 대해 생성되지 않습니다. 스택에 이 형식의 개체를 만들려고 하면 컴파일러 오류가 발생합니다.  
  
 다음 샘플에서는 C4624를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C4624.cpp  
// compile with: /W1 /c  
class B {  
// Uncomment the following line to fix.  
// public:  
   ~B();  
};  
  
class D : public B {};   // C4624 B's destructor not public  
```