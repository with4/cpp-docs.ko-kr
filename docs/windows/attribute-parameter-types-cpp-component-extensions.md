---
title: 특성 매개 변수 형식 (c + + 구성 요소 확장) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, parameter types
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 79d89eec82725b28bdbe43f08ac2c05cdb889f6e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466971"
---
# <a name="attribute-parameter-types--c-component-extensions"></a>특성 매개 변수 형식(C++ 구성 요소 확장)
특성에 전달된 값은 컴파일 타임에 컴파일러에 알려야 합니다.  특성 매개 변수는 다음 형식일 수 있습니다.  
  
-   **bool**  
  
-   **char**, **unsigned char**  
  
-   **short**, **unsigned short**  
  
-   **int**, **부호 없는 int**  
  
-   **긴**, **부호 없는 long**  
  
-   **__int64**, **unsigned __int64**  
  
-   **부동 소수점**, **double**  
  
-   **wchar_t**  
  
-   `char*`, `wchar_t*` 또는 `System::String*`  
  
-   `System::Type ^`  
  
-   `System::Object ^`  
  
-   **enum**  
  
## <a name="example"></a>예  
  
### <a name="code"></a>코드  
  
```cpp  
// attribute_parameter_types.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct AStruct {};  
  
[AttributeUsage(AttributeTargets::ReturnValue)]  
ref struct Attr : public Attribute {  
   Attr(AStruct ^ i){}  
   Attr(bool i){}  
   Attr(){}  
};  
  
ref struct MyStruct {  
   static AStruct ^ x = gcnew AStruct;  
   [returnvalue:Attr(x)] int Test() { return 0; }   // C3104  
   [returnvalue:Attr] int Test2() { return 0; }   // OK  
   [returnvalue:Attr(true)] int Test3() { return 0; }   // OK  
};  
```  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 특성을 지정할 때 명명되지 않은 모든 (위치) 인수는 모든 명명된 인수 앞에 와야 합니다.  
  
### <a name="code"></a>코드  
  
```cpp  
// extending_metadata_c.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class)]  
ref class MyAttr : public Attribute {  
public:  
   MyAttr() {}  
   MyAttr(int i) {}  
   property int Priority;  
   property int Version;  
};  
  
[MyAttr]   
ref class ClassA {};   // No arguments  
  
[MyAttr(Priority = 1)]   
ref class ClassB {};   // Named argument  
  
[MyAttr(123)]   
ref class ClassC {};   // Positional argument  
  
[MyAttr(123, Version = 1)]   
ref class ClassD {};   // Positional and named  
```  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 특성 매개 변수는 이전 형식의 1차원 배열일 수 있습니다.  
  
### <a name="code"></a>코드  
  
```cpp  
// extending_metadata_d.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::Class)]  
public ref struct ABC : public Attribute {  
   ABC(array<int>^){}  
   array<double> ^ param;  
};  
  
[ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]   
ref struct AStruct{};  
```  
  
## <a name="see-also"></a>참고 항목  
 [사용자 정의 특성](../windows/user-defined-attributes-cpp-component-extensions.md)