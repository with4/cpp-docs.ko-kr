---
title: "How to: Improve Performance with Generics (Visual C++) | Microsoft Docs"
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
  - "performance, C++"
  - "Visual C++, performance"
  - "Visual C++, generics"
  - "generics [C++], performance"
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
caps.latest.revision: 7
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Improve Performance with Generics (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제네릭을 이용해 재사용 가능한 코드를 기반으로 형식 매개 변수를 만들 수 있습니다.  형식 매개 변수의 실제 형식은 클라이언트 코드에서 호출 될 때까지 지 됩니다.  제네릭에 대한 자세한 내용은 [Generics](../windows/generics-cpp-component-extensions.md)을 참조하십시오.  
  
 이 문서에서는 어떻게 제네릭 컬렉션을 사용하는 응용 프로그램의 성능을 향상 시킬 수 있는지 설명합니다.  
  
## 예제  
 .NET Framework는 <xref:System.Collections?displayProperty=fullName> 네임 스페이스의 여러 컬렉션 클래스를 가집니다.  대부분 이러한 컬렉션은 <xref:System.Object?displayProperty=fullName> 형식의 개체에서 동작합니다.  . NET 프레임 워크, 심지어는 값 형식의 모든 종류의 <xref:System.Object?displayProperty=fullName>에서 파생 된 이후이 컬렉션의 모든 유형을 저장할 수 있습니다  그러나이 방법에는 두 가지 단점이 있습니다.  
  
 컬렉션이 같은 정수로 값 형식을 저장하는 경우, 최초로,이 값은 값이 컬렉션에서 검색되는 컬렉션 및 unboxed에 추가되기 전에 box되어야 합니다.  비용이 많이 드는 작업입니다.  
  
 둘째, 형식은 컬렉션에 추가 할 수있는 제어 방법이 없습니다.  이것은 의도 된 것은 아마 아닐지라도 동일한 컬렉션에 정수와 문자열을 추가하는 것은 가능하다.  따라서 형식 안전 위하여 코드를 위해 컬렉션에서 가져온 형식이 원하는 것임을 확인해야합니다.  
  
 다음 코드 예제에서는 제네릭 전 .NET Framework 컬렉션의 두 가지 주요 단점이 보여줍니다.  
  
```  
// perf_pre_generics.cpp  
// compile with: /clr  
  
using namespace System;  
using namespace System::Collections;  
  
int main()  
{  
    // This Stack can contain any type.  
    Stack ^s = gcnew Stack();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
  
    // Push a String to the same Stack.  
    // The Stack now contains two different data types.  
    s->Push("Seven");  
  
    // Pop the items off the Stack.  
    // The item is returned as an Object, so a cast is  
    // necessary to convert it to its proper type.  
    while (s->Count > 0)  
    {  
        Object ^o = s->Pop();  
        if (o->GetType() == Type::GetType("System.String"))  
        {  
            Console::WriteLine("Popped a String: {0}", (String ^)o);  
        }  
        else if (o->GetType() == Type::GetType("System.Int32"))  
        {  
            Console::WriteLine("Popped an int: {0}", (int)o);  
        }  
        else  
        {  
            Console::WriteLine("Popped an unknown type!");  
        }  
    }  
}  
```  
  
  **문자열을 팝합니다: 7**  
**Int 팝: 7**   
## 예제  
 새 <xref:System.Collections.Generic?displayProperty=fullName> 네임 스페이스는 <xref:System.Collections?displayProperty=fullName> 네임 스페이스에서 찾을 수 있는 여러 개의 동일한 컬렉션의 포함하고 있습니다. 하지만 제네릭 형식 매개 변수를 사용하여 수정된 것입니다.  이렇게 하면 제네릭이 아닌 컬렉션의 두 가지 단점이 사라집니다: boxing 및 unboxing 컬렉션에 저장 될 값 형식과 종류를 지정할 수 있습니다.  두 컬렉션에 대한 작업은 동일 합니다. 인스턴스화 방법만 다릅니다.  
  
 제네릭 <xref:System.Collections.Generic.Stack%601> 컬렉션 예제를 사용하여 위에서 작성된 예제를 비교합니다.  자주 액세스되는 큰 컬렉션에서이 예제의 성능은 앞의 예보다 훨씬 클 것입니다.  
  
```  
// perf_post_generics.cpp  
// compile with: /clr  
  
#using <System.dll>  
  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main()  
{  
    // This Stack can only contain integers.  
    Stack<int> ^s = gcnew Stack<int>();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
    s->Push(14);  
  
    // You can no longer push a String to the same Stack.  
    // This will result in compile time error C2664.  
    //s->Push("Seven");  
  
    // Pop an item off the Stack.  
    // The item is returned as the type of the collection, so no  
    // casting is necessary and no unboxing is performed for  
    // value types.  
    int i = s->Pop();  
    Console::WriteLine(i);  
  
    // You can no longer retrieve a String from the Stack.  
    // This will result in compile time error C2440.  
    //String ^str = s->Pop();  
}  
```  
  
  **14**   
## 참고 항목  
 [Generics](../windows/generics-cpp-component-extensions.md)