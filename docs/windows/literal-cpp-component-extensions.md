---
title: 리터럴 (c + + 구성 요소 확장) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- literal
- literal_cpp
dev_langs:
- C++
helpviewer_keywords:
- literal keyword [C++]
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 78dda3c52192b0d2755bdc8f8944eb0e1443e7af
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604176"
---
# <a name="literal-c-component-extensions"></a>리터럴(C++ 구성 요소 확장명)
변수 (데이터 멤버)로 표시 **리터럴** 에 **/clr** 해당 하는 네이티브 컴파일이 **정적 const** 변수.  
  
## <a name="all-platforms"></a>모든 플랫폼  
### <a name="remarks"></a>설명 
  
 (이 언어 기능에는 모든 런타임에 적용되는 설명이 없습니다.)  
  
## <a name="windows-runtime"></a>Windows 런타임  
### <a name="remarks"></a>설명 
  
 (이 언어 기능에는 Windows 런타임에만 적용되는 설명이 없습니다.)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
  
## <a name="remarks"></a>설명  
 으로 표시 된 데이터 멤버 **리터럴** 선언할 때 초기화 해야 하며 정수 계열 상수, 열거형 또는 문자열 형식의 값 이어야 합니다. 초기화 식의 형식에서 정적 const 데이터 멤버의 형식으로 변환하는 데 사용자 정의 변환이 필요 없어야 합니다.  
  
 메모리는 런타임에 리터럴 필드에 대해 할당되지 않습니다. 컴파일러는 클래스에 대한 메타데이터에 해당 값을 삽입하기만 합니다.  
  
 변수 표시 **정적 const** 다른 컴파일러가 메타 데이터에서 사용할 수 없습니다.  
  
 자세한 내용은 [정적](../cpp/storage-classes-cpp.md) 하 고 [const](../cpp/const-cpp.md)합니다.  
  
 **리터럴** 상황에 맞는 키워드입니다. 참조 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md) 자세한 내용은 합니다.  
  
## <a name="example"></a>예  
 이 예에서는 한 **리터럴** 변수에 의미 **정적**합니다.  
  
```cpp  
// mcppv2_literal.cpp  
// compile with: /clr  
ref struct X {  
   literal int i = 4;  
};  
  
int main() {  
   int value = X::i;  
}  
```  
  
## <a name="example"></a>예  
 다음 샘플에서는 메타데이터에서 리터럴의 영향을 보여 줍니다.  
  
```cpp  
// mcppv2_literal2.cpp  
// compile with: /clr /LD  
public ref struct A {  
   literal int lit = 0;  
   static const int sc = 1;  
};  
```  
  
 `sc` 및 `lit`에 대한 메타데이터에서의 차이점을 확인할 수 있습니다. `modopt` 지시문은 `sc`에 적용되어, 다른 컴파일러에서 무시될 수 있습니다.  
  
```  
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)  
```  
  
```  
.field public static literal int32 lit = int32(0x0000000A)  
```  
  
## <a name="example"></a>예  
 다음 샘플에서는 C#에서 작성 된 이전 샘플에서 만든 메타 데이터를 참조 하 고 영향을 보여 줍니다 **리터럴** 하 고 **정적 const** 변수:  
  
```cs  
// mcppv2_literal3.cs  
// compile with: /reference:mcppv2_literal2.dll  
// A C# program  
class B {  
   public static void Main() {  
      // OK  
      System.Console.WriteLine(A.lit);  
      System.Console.WriteLine(A.sc);  
  
      // C# does not enforce C++ const  
      A.sc = 9;  
      System.Console.WriteLine(A.sc);  
  
      // C# enforces const for a literal  
      A.lit = 9;   // CS0131  
  
      // you can assign a C++ literal variable to a C# const variable  
      const int i = A.lit;  
      System.Console.WriteLine(i);  
  
      // but you cannot assign a C++ static const variable  
      // to a C# const variable  
      const int j = A.sc;   // CS0133  
      System.Console.WriteLine(j);  
   }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)