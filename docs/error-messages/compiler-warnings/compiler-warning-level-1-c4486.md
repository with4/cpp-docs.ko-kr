---
title: 컴파일러 경고 (수준 1) C4486 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4486
dev_langs:
- C++
helpviewer_keywords:
- C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91ad3659660dbe17552dc46caa66afe274ace9cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280779"
---
# <a name="compiler-warning-level-1-c4486"></a>컴파일러 경고(수준 1) C4486
'function': ref 클래스 또는 값 클래스의 전용 가상 메서드를 'sealed'으로 표시  
  
 이후 전용 가상 멤버 함수는 관리 되는 클래스 또는 구조체의 액세스 또는 재정의 될 수 없습니다, 표시 해야 [봉인](../../windows/sealed-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4486 오류가 발생 합니다.  
  
```  
// C4486.cpp  
// compile with: /clr /c /W1  
ref class B {  
private:  
   virtual void f() {}   // C4486  
   virtual void f1() sealed {}   // OK  
};  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 사용 하는 전용 sealed로 표시 된 가상 함수를 보여 줍니다.  
  
```  
// C4486_b.cpp  
// compile with: /clr /c  
ref class B {};  
  
ref class D : B {};  
  
interface class I {  
   B^ mf();  
};  
  
ref class E : I {  
private:  
   virtual B^ g() sealed = I::mf {  
      return gcnew B;  
   }  
  
public:  
   virtual D^ mf() {  
      return gcnew D;  
   }  
};  
```