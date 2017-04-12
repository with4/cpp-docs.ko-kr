---
title: "컴파일러 오류 C3390 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3390
dev_langs:
- C++
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 257b0678ded15815f6673091d1adb26dea1dec12
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3390"></a>컴파일러 오류 C3390
'type_arg': 제네릭 'generic_type'의 제네릭 매개 변수 'param'에 대한 형식 인수가 잘못되었습니다. 참조 형식이어야 합니다.  
  
제네릭 형식이 잘못 인스턴스화되었습니다.  형식 정의를 확인하세요.  자세한 내용은 참조 [제네릭](../../windows/generics-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
C +의 제네릭 형식을 만들 때 지원 되지 않는 특정 제약 조건이 있는 제네릭 형식을 포함 하는 구성 요소를 만드는 첫 번째 샘플에서는 C# + CLR 합니다. 자세한 내용은 참조 [형식 매개 변수에 대 한 제약 조건을](/dotnet/articles/csharp/programming-guide/generics/constraints-on-type-parameters)합니다.  
  
```cs  
// C3390.cs  
// Compile by using: csc /target:library C3390.cs  
// a C# program  
public class GR<C, V, N>  
where C : class  
where V : struct  
where N : new() {}  
```  
  
C3390.dll 구성 요소를 사용할 수 있는 다음 샘플에서는 C3390 오류가 발생 합니다.  
  
```cpp  
// C3390_b.cpp  
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>  
ref class R { R(int) {} };  
value class V {};  
ref struct N { N() {} };  
  
int main () {  
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type  
   GR<R^, V, N^>^ gr2b; // OK  
}  
```
