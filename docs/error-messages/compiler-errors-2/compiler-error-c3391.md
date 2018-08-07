---
title: 컴파일러 오류 C3391 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3391
dev_langs:
- C++
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28615d85eca534966a4d8b90cef20ea577e0d592
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256616"
---
# <a name="compiler-error-c3391"></a>컴파일러 오류 C3391
'type_arg': 제네릭 'generic_type'의 ' param' 제네릭 매개 변수에 대 한 잘못 된 형식 인수가 nullable이 아닌 값 형식 이어야 합니다.  
  
제네릭 형식이 잘못 인스턴스화되었습니다. 형식 정의를 확인하세요. 자세한 내용은 참조 <xref:System.Nullable> 및 [제네릭](../../windows/generics-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
C + 제네릭 형식을 제작 하는 경우 지원 되지 않는 특정 제약 조건을 가진 제네릭 형식을 포함 하는 구성 요소를 만들려면 다음 샘플에서는 C# + CLI 합니다. 자세한 내용은 [형식 매개 변수에 대한 제약 조건](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)을 참조하세요.  
  
```cs  
// C3391.cs  
// Compile by using: csc /target:library C3391.cs  
// a C# program  
public class GR<N>  
where N : struct {}  
```  
  
C3391.dll 구성 요소를 사용할 수 있는 다음 샘플에서는 c 3391을 생성 합니다.  
  
```cpp  
// C3391_b.cpp  
// Compile by using: cl /clr C3391_b.cpp  
#using <C3391.dll>  
using namespace System;  
value class VClass {};  
  
int main() {  
   GR< Nullable<VClass> >^ a =   
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable  
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK  
}  
```