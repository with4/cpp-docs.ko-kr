---
title: "컴파일러 오류 C3104 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3104
dev_langs:
- C++
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 5df018fe26e66ed480ed2464c19c876adfac8dd1
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3104"></a>컴파일러 오류 C3104
특성 인수가 잘못되었습니다.  
  
 특성에 잘못 된 인수를 지정 했습니다.  
  
 참조 [특성 매개 변수 형식](../../windows/attribute-parameter-types-cpp-component-extensions.md) 에 대 한 자세한 내용은 합니다.  
  
 이 오류는 Visual c + + 2005에 대해 수행 된 컴파일러 규칙의 결과로 생성 될 수 없습니다: 관리 되는 배열, 사용자 지정 특성에 전달 하는 경우 배열의 형식은 집합체 초기화 목록에서 더 이상 추론 됩니다. 이제 컴파일러를 요구 이니셜라이저 목록 뿐 아니라 배열 형식을 지정할 수 있습니다.  
  
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

