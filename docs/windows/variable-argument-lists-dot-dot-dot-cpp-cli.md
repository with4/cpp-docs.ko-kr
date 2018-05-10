---
title: 가변 인수 목록 (...) (C + + /CLI CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eec0e3591da2417137fda3bae4ed9e7860472fb2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="variable-argument-lists--ccli"></a>가변 인수 목록(...)(C++/CLI)
사용 하는 방법을 보여 주는이 예제는 `...` Visual c + + 가변 개수의 인수는 함수를 구현 하는 구문입니다.  
  
> [!NOTE]
>  이 항목 관련 C + + /cli CLI 합니다. 사용 하는 방법에 대 한 내용은 `...` ISO 표준 c + +에서 참조 [Ellipses 및 Variadic 템플릿](../cpp/ellipses-and-variadic-templates.md) 줄임표 및 기본 인수에 및 [후 위 식](../cpp/postfix-expressions.md)합니다.  
  
 매개 변수를 사용 하 여 `...` 매개 변수 목록의 마지막 매개 변수 여야 합니다.  
  
## <a name="example"></a>예제  
  
### <a name="code"></a>코드  
  
```  
// mcppv2_paramarray.cpp  
// compile with: /clr  
using namespace System;  
double average( ... array<Int32>^ arr ) {  
   int i = arr->GetLength(0);  
   double answer = 0.0;  
  
   for (int j = 0 ; j < i ; j++)  
      answer += arr[j];  
  
   return answer / i;  
}  
  
int main() {  
   Console::WriteLine("{0}", average( 1, 2, 3, 6 ));  
}  
```  
  
### <a name="output"></a>출력  
  
```  
3  
```  
  
## <a name="code-example"></a>코드 예제  
 다음 예제에서는 C#에서 가변 개수의 인수를 사용 하는 Visual c + + 함수를 호출 하는 방법을 보여 줍니다.  
  
```  
// mcppv2_paramarray2.cpp  
// compile with: /clr:safe /LD  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
```  
  
 함수 `f` 에서 호출할 수 있는 C# 또는 Visual Basic의 경우 예를 들어 가변 개수의 인수를 사용할 수 있는 함수를 것 처럼 합니다.  
  
 C#에서에 전달 되는 인수는 `ParamArray` 가변 개수의 인수에서 매개 변수를 호출할 수 있습니다. 다음 코드 예제는 C#입니다.  
  
```  
// mcppv2_paramarray3.cs  
// compile with: /r:mcppv2_paramarray2.dll  
// a C# program  
  
public class X {  
   public static void Main() {  
      // Visual C# will generate a String array to match the   
      // ParamArray attribute  
      C myc = new C();  
      myc.f("hello", "there", "world");  
   }  
}  
```  
  
 에 대 한 호출 `f` Visual c + +에서는 초기화 된 배열 또는 가변 길이 배열을 전달할 수 있습니다.  
  
```  
// mcpp_paramarray4.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
  
int main() {  
   C ^ myc = gcnew C();  
   myc->f("hello", "world", "!!!");  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [배열](../windows/arrays-cpp-component-extensions.md)