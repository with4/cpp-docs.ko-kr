---
title: "for each, in | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::foreach"
  - "for"
  - "each"
  - "in"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for each 키워드[C++]"
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# for each, in
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

배열 또는 컬렉션을 반복합니다.  이 비표준 키워드는 C\+\+\/CLI 및 네이티브 C\+\+ 프로젝트에서 사용할 수 있습니다.  그러나 사용하지 않는 것이 좋습니다.  대신 표준 [범위 기반 for 문\(C\+\+\)](../cpp/range-based-for-statement-cpp.md)를 사용하십시오.  
  
## 모든 런타임  
 **구문**  
  
```  
  
        for each (type identifier in expression) {  
   statements  
}  
  
```  
  
 **매개 변수**  
  
 `type`  
 `identifier`의 형식입니다.  
  
 `identifier`  
 반복 변수는 컬렉션 요소를 나타냅니다.  `identifier`가 [Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md)인 경우 요소를 수정할 수 있습니다.  
  
 `expression`  
 배열 식 또는 컬렉션입니다.  컬렉션 요소는 컴파일러가 `identifier` 형식으로 변환할 수 있어야 합니다.  
  
 `statements`  
 실행할 하나 이상의 문입니다.  
  
 **설명**  
  
 `for each` 문은 컬렉션을 반복하는 데 사용됩니다.  컬렉션의 요소를 수정할 수 있지만 요소를 추가하거나 삭제할 수 없습니다.  
  
 *statements*는 배열 또는 컬렉션의 각 요소에 대해 실행됩니다.  컬렉션의 모든 요소에 대해 반복이 완료된 후 제어가 `for each` 블록 다음 문으로 전달됩니다.  
  
 `for each` 및 `in`은 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)입니다.  
  
 추가 정보  
  
-   [for each를 사용하여 STL 컬렉션 반복](../dotnet/iterating-over-stl-collection-by-using-for-each.md)  
  
-   [방법: for each로 배열 반복](../dotnet/how-to-iterate-over-arrays-with-for-each.md)  
  
-   [방법: for each로 제네릭 컬렉션 반복](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)  
  
-   [방법: for each로 사용자 정의 컬렉션 반복](../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
### 예제  
 이 예제는 `for each`를 사용해서 문자열을 반복하는 방법을 보여줍니다.  
  
```  
// for_each_string1.cpp  
// compile with: /ZW  
#include <stdio.h>  
using namespace Platform;  
  
ref struct MyClass {  
   property String^ MyStringProperty;  
};  
  
int main() {  
   String^ MyString = ref new String("abcd");  
  
   for each ( char c in MyString )  
      wprintf("%c", c);  
  
   wprintf("/n");  
  
   MyClass^ x = ref new MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( char c in x->MyStringProperty )  
      wprintf("%c", c);  
}  
```  
  
 **Output**  
  
  **abcd**  
 **테스트**   
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **설명**  
  
 CLR 구문은 다음을 제외한 **모든 런타임** 구문과 같습니다.  
  
 *expression*  
 관리되는 배열 식 또는 컬렉션입니다.  컬렉션 요소는 컴파일러가 <xref:System.Object>에서 *identifier* 형식으로 변환할 수 있는 형식이어야 합니다.  
  
 *expression*은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 형식 또는 <xref:System.Collections.IEnumerator>를 구현하거나 `IEnumerator`에 정의된 모든 메서드를 선언하는 형식을 반환하는 `GetEnumerator` 메서드를 정의하는 형식으로 평가합니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 이 예제는 `for each`를 사용해서 문자열을 반복하는 방법을 보여줍니다.  
  
```  
// for_each_string2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct MyClass {  
   property String ^ MyStringProperty;  
};  
  
int main() {  
   String ^ MyString = gcnew String("abcd");  
  
   for each ( Char c in MyString )  
      Console::Write(c);  
  
   Console::WriteLine();  
  
   MyClass ^ x = gcnew MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( Char c in x->MyStringProperty )  
      Console::Write(c);  
}  
```  
  
 **Output**  
  
  **abcd**  
 **테스트**    
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)