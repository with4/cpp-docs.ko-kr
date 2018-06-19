---
title: 컴파일러 경고 (수준 1) C4461 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4461
dev_langs:
- C++
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2884daeb7497f6664cecf864ec705891cac62f48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278635"
---
# <a name="compiler-warning-level-1-c4461"></a>컴파일러 경고(수준 1) C4461
'type':이 클래스에 'finalizer'는 종료 자가 있지만 'dtor' 소멸자가 없습니다  
  
 형식에 종료자의 존재를 삭제 하는 리소스를 의미 합니다. 명시적으로 해당 형식의 소멸자에서 종료자를 호출 하지 않으면 공용 언어 런타임 개체가 범위를 벗어난 후 하면 종료 자가 실행 시기를 결정 합니다.  
  
 형식에 소멸자를 정의 하 고 명시적으로 소멸자에서 종료자를 호출 하는 경우 종료자를 명확 하 게 실행할 수 있습니다.  
  
 자세한 내용은 참조 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4461 오류가 발생 합니다.  
  
```  
// C4461.cpp  
// compile with: /W1 /clr /c  
ref class A {  
protected:  
   !A() {}   // C4461  
};  
  
// OK  
ref struct B {  
   ~B() {  
      B::!B();  
   }  
  
   !B() {}  
};  
```