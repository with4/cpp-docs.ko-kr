---
title: 컴파일러 오류 C2885 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2885
dev_langs:
- C++
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f37ea0f9fadb74b44eea5ad110f7f12b884f0e41
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2885"></a>컴파일러 오류 C2885
'class::identifier': 하지 유효한 using 선언에서 비 클래스 범위로  
  
 사용한는 [를 사용 하 여](../../cpp/using-declaration.md) 선언 잘못 합니다.  
  
## <a name="example"></a>예제  
 이 오류는 Visual c + + 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 없습니다: 다은 더 이상는 `using` 중첩된 형식이 선언을 이름을에 형식을 배치 하는 중첩 형식 선언을 명시적으로 정규화 해야 공간, 또는 typedef를 만들어야 합니다.  
  
 다음 샘플에서는 C2885 오류가 발생 합니다.  
  
```  
// C2885.cpp  
namespace MyNamespace {  
   class X1 {};  
}  
  
struct MyStruct {  
   struct X1 {  
      int i;  
   };  
};  
  
int main () {  
   using MyStruct::X1;   // C2885  
  
   // OK  
   using MyNamespace::X1;  
   X1 myX1;  
  
   MyStruct::X1 X12;  
  
   typedef MyStruct::X1 abc;  
   abc X13;  
   X13.i = 9;  
}  
```  
  
## <a name="example"></a>예제  
 사용 하는 경우는 `using` 키워드와 c + + 클래스 멤버 (파생된 클래스)의 다른 클래스 안에 해당 멤버를 정의 해야 합니다.  
  
 다음 샘플에서는 C2885 오류가 발생 합니다.  
  
```  
// C2885_b.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
};  
  
void z() {  
   using A::i;   // C2885 not in a class  
}  
  
class B : public A {  
public:  
   using A::i;  
};  
```