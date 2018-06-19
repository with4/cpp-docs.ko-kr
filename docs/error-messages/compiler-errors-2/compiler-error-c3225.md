---
title: 컴파일러 오류 C3225 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3225
dev_langs:
- C++
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f9f6691ddacf6b3c1347b9fd4cac134433741a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250581"
---
# <a name="compiler-error-c3225"></a>컴파일러 오류 C3225
'arg'에 대 한 제네릭 형식 인수는 'type' 일 수 없습니다, 그리고 값 형식 이어야 하거나 형식을 처리 해야 합니다.  
  
 제네릭 형식 인수는 올바른 유형이 아니었습니다.  
  
 자세한 내용은 [제네릭](../../windows/generics-cpp-component-extensions.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 네이티브 형식으로 제네릭 형식을 인스턴스화할 수 없습니다. 다음 샘플에서는 C3225 오류가 발생 합니다.  
  
```  
// C3225.cpp  
// compile with: /clr  
class A {};  
  
ref class B {};  
  
generic <class T>  
ref class C {};  
  
int main() {  
   C<A>^ c = gcnew C<A>;   // C3225  
   C<B^>^ c2 = gcnew C<B^>;   // OK  
}  
```  
  
## <a name="example"></a>예제  
 다음 샘플 C#을 사용 하는 구성 요소를 만듭니다. 제약 조건이 제네릭 형식 값 형식과 함께 힙에서만 인스턴스화할 수를 지정 하는 확인 합니다.  
  
```  
// C3225_b.cs  
// compile with: /target:library  
// a C# program  
public class MyList<T> where T: struct {}  
```  
  
## <a name="example"></a>예제  
 이 샘플은 C# 사용.-구성 요소를 작성 하 고 MyList만 될 수 있는 제약 조건을 위반 아닌 다른 값 형식과 함께 인스턴스화할 <xref:System.Nullable>합니다. 다음 샘플에서는 C3225 오류가 발생 합니다.  
  
```  
// C3225_c.cpp  
// compile with: /clr  
#using "C3225_b.dll"  
ref class A {};  
value class B {};  
int main() {  
   MyList<A> x;   // C3225  
   MyList<B> y;   // OK  
}  
```