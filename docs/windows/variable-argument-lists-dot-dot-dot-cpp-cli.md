---
title: "Variable Argument Lists (...) (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "variable argument lists"
  - "parameter arrays"
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Variable Argument Lists (...) (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 예제는 Visual C\+\+에서 `...` 구문을 사용하여 여러 인수를 갖는 함수를 구현하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 항목은 C\+\+\/CLI에 적용됩니다.  ISO Standard C\+\+에서 `...`를 사용하는 방법은 [Ellipses 및 Variadic 템플릿](../cpp/ellipses-and-variadic-templates.md) 및 [줄임표 및 기본 인수](../misc/ellipses-and-default-arguments.md)를 참조하십시오.  
  
 `...`를 사용하는 매개 변수는 매개 변수 목록에서 마지막 매개 변수여야 합니다.  
  
## 예제  
  
### 코드  
  
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
  
### Output  
  
```  
3  
```  
  
## 코드 예제  
 다음 예제는 C\#에서 다양한 수의 인수를 갖는 Visual C\+\+를 호출하는 방법을 보여 줍니다.  
  
```  
// mcppv2_paramarray2.cpp  
// compile with: /clr:safe /LD  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
```  
  
 `f` 함수는 다양한 수의 인수를 사용할 수 있는 함수처럼 C\# 또는 Visual Basic에서 호출할 수 있습니다.  
  
 C\#에서 `ParamArray` 매개 변수로 전달되는 인수는 인수의 변수 번호로 호출할 수 있습니다.  다음은 C\#의 코드 샘플입니다.  
  
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
  
 Visual C\+\+에서 `f`에 대한 호출은 초기화된 배열 또는 가변 길이 배열을 전달할 수 있습니다.  
  
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
  
## 참고 항목  
 [Arrays](../windows/arrays-cpp-component-extensions.md)