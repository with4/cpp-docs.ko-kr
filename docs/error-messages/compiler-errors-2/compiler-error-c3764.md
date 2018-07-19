---
title: 컴파일러 오류 C3764 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3764
dev_langs:
- C++
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c214fcf40f442c35d754db64c8443c328d50ae10
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273630"
---
# <a name="compiler-error-c3764"></a>컴파일러 오류 C3764
'override_function': 기본 클래스 메서드 'base_class_function'를 재정의할 수 없습니다  
  
 컴파일러가 잘못 재정의 검색 했습니다. 예를 들어 기본 클래스 함수는 없습니다 `virtual`합니다. 자세한 내용은 참조 [재정의](../../windows/override-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3764 오류가 발생 합니다.  
  
```  
// C3764.cpp  
// compile with: /clr /c  
public ref struct A {  
   void g(int);  
   virtual void h(int);  
};  
  
public ref struct B : A {  
   virtual void g(int) override {}   // C3764  
   virtual void h(int) override {}   // OK  
};  
```  
  
## <a name="example"></a>예제  
 C3764 기본 클래스 메서드를 둘 다 명시적으로 하는 경우에 발생할 수 있습니다 및 명명 된 재정의 합니다. 다음 샘플에서는 C3764 오류가 발생 합니다.  
  
```  
// C3764_b.cpp  
// compile with: /clr /c  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : public A {  
   virtual void Test() override {}  
   virtual void Test2() = A::Test {}   // C3764  
};  
```