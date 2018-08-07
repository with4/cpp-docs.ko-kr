---
title: 컴파일러 오류 C3104 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3104
dev_langs:
- C++
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ded5185e3f87ce7f1b5a4a7015ce3c4476c949b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246469"
---
# <a name="compiler-error-c3104"></a>컴파일러 오류 C3104
잘못 된 특성 인수입니다.  
  
 특성에 잘못 된 인수를 지정 했습니다.  
  
 참조 [특성 매개 변수 형식](../../windows/attribute-parameter-types-cpp-component-extensions.md) 자세한 정보에 대 한 합니다.  
  
 이 오류는 Visual c + + 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 없습니다: 관리 되는 배열, 사용자 지정 특성에 전달 하는 경우 배열의 형식을 집합체 초기화 목록에서 더 이상 추론 됩니다. 이제 컴파일러에 필요으로 배열 이니셜라이저 목록 형식을 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3104 오류가 발생 합니다.  
  
```  
// C3104a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::Class)]  
public ref struct ABC : public Attribute {  
   ABC(array<int>^){}  
   array<double> ^ param;  
};  
  
[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104  
// try the following line instead  
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]   
ref struct AStruct{};  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3104 오류가 발생 합니다.  
  
```  
// C3104b.cpp  
// compile with: /clr /c  
// C3104 expected  
using namespace System;  
  
int func() {  
   return 0;   
}  
  
[attribute(All)]  
ref class A {  
public:   
   A(int) {}  
};  
  
// Delete the following 2 lines to resolve.  
[A(func())]  
ref class B {};  
  
// OK  
[A(0)]  
ref class B {};  
```  
