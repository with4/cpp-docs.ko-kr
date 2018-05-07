---
title: 컴파일러 경고 (수준 1) C4489 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4489
dev_langs:
- C++
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1c6cff47d8788edd7fdba6844e07d59654456a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4489"></a>컴파일러 경고(수준 1) C4489
'specifier': 인터페이스 메서드 'method';에 사용할 수 없습니다 재정의 지정자는 ref 클래스와 값 클래스 메서드에만 사용할 수  
  
 지정자 키워드에 인터페이스 메서드가 잘못 사용 했습니다.  
  
 자세한 내용은 참조 [재정의 지정자](../../windows/override-specifiers-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4489 경고가 발생 합니다.  
  
```  
// C4489.cpp  
// compile with: /clr /c /W1  
public interface class I {   
   void f() new;   // C4489  
   virtual void b() override;   // C4489  
  
   void g();   // OK  
};  
```