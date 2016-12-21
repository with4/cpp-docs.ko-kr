---
title: "typeid(C++ 구성 요소 확장) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "typeid 키워드[C++]"
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
caps.latest.revision: 35
caps.handback.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# typeid(C++ 구성 요소 확장)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

개체 형식을 나타내는 값을 가져옵니다.  
  
> [!WARNING]
>  이 항목은 typeid의 C\+\+ 구성 요소 확장 버전을 참조합니다.  이 키워드의 ISO C\+\+버전은, [typeid 연산자](../cpp/typeid-operator.md)을 참조하십시오.  
  
## 모든 런타임  
  
### 구문  
  
```cpp  
  
T::typeid  
```  
  
### 매개 변수  
 *T*  
 형식 이름입니다.  
  
## Windows 런타임\(Windows Runtime\)  
  
### 구문  
  
```cpp  
Platform::Type^ type = T::typeid;  
```  
  
### 매개 변수  
 `T`  
 형식 이름입니다.  
  
### 설명  
 [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]에서, typeid는 런타임 형식 정보에서 생성된 [Platform::Type](../Topic/Platform::Type%20Class.md)을 반환합니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **구문**  
  
```  
  
type::typeid  
```  
  
 **매개 변수**  
  
 *type*  
 System::Type 개체에 적용할 형식의 이름\(추상 선언자\)입니다.  
  
 **설명**  
  
 `typeid`는 컴파일 시간에 형식에 대한 <xref:System.Type>을 가져오는 데 사용됩니다.  
  
 `typeid`는 <xref:System.Type.GetType%2A> 또는 <xref:System.Object.GetType%2A>을 사용하여 런타임에 형식에 대해 System::Type을 가져오는 것과 비슷합니다.  그러나 typeid는 형식 이름만 매개 변수로 받습니다.  형식 인스턴스를 사용하여 System::Type 이름을 가져오려는 경우 GetType을 사용합니다.  
  
 `typeid`는 컴파일 시간에 형식 이름\(type\)을 평가할 수 있는 반면, GetType은 런타임에 반환할 형식을 평가할 수 있어야 합니다.  
  
 `typeid`는 네이티브 형식 이름 또는 네이티브 형식 이름에 대한 공용 언어 런타임 별칭을 사용할 수 있습니다. 자세한 내용은 [C\+\+ 네이티브 형식에 해당하는 .NET Framework](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)을 참조하십시오.  
  
 `typeid` 역시 여전히 System::Type을 반환하기는 하지만 네이티브 형식에서 작동합니다.  type\_info 구조를 가려오려면 [typeid 연산자](../cpp/typeid-operator.md)를 사용합니다.  
  
 `typeid`는 이전 **\/clr** 구문에서 [\_\_typeof](../misc/typeof.md)의 후속 작업입니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 예제에서는 typeid 키워드를 GetType\(\) 멤버와 비교합니다.  
  
```  
// keyword__typeid.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   Type ^ pType = pG->GetType();  
   Type ^ pType2 = G::typeid;  
  
   if (pType == pType2)  
      Console::WriteLine("typeid and GetType returned the same System::Type");  
   Console::WriteLine(G::typeid);  
  
   typedef float* FloatPtr;  
   Console::WriteLine(FloatPtr::typeid);  
}  
```  
  
 **Output**  
  
  **typeid 및 GetType에서 동일한 System::Type를 반환함**  
**G**  
 **System.Single\*** **예제**  
  
 다음 샘플에서는 형식 System::Type의 변수를 형식에 대한 특성을 가져오는 데 사용할 수 있음을 보여줍니다.  또한 일부 형식의 경우 typedef를 만들어 `typeid`를 사용해야 함을 보여줍니다.  
  
```  
// keyword__typeid_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Security;  
using namespace System::Security::Permissions;  
  
typedef int ^ handle_to_int;  
typedef int * pointer_to_int;  
  
public ref class MyClass {};  
  
class MyClass2 {};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass {  
public:  
   AtClass(Type ^) {  
      Console::WriteLine("in AtClass Type ^ constructor");  
   }  
};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass2 {  
public:  
   AtClass2() {  
      Console::WriteLine("in AtClass2 constructor");  
   }  
};  
  
// Apply the AtClass and AtClass2 attributes to class B  
[AtClass(MyClass::typeid), AtClass2]     
[AttributeUsage(AttributeTargets::All)]  
ref class B : Attribute {};  
  
int main() {  
   Type ^ MyType = B::typeid;  
  
   Console::WriteLine(MyType->IsClass);  
  
   array<Object^>^ MyArray = MyType -> GetCustomAttributes(true);  
   for (int i = 0 ; i < MyArray->Length ; i++ )  
      Console::WriteLine(MyArray[i]);  
  
   if (int::typeid != pointer_to_int::typeid)  
      Console::WriteLine("int::typeid != pointer_to_int::typeid, as expected");  
  
   if (int::typeid == handle_to_int::typeid)  
      Console::WriteLine("int::typeid == handle_to_int::typeid, as expected");  
}  
```  
  
 **Output**  
  
  **True**  
 **in AtClass2 constructor**  
 **in AtClass Type ^ constructor**  
 **AtClass2**  
 **System.AttributeUsageAttribute**  
 **AtClass**  
 **int::typeid \!\= pointer\_to\_int::typeid, 예상됨**  
 **int::typeid \=\= handle\_to\_int::typeid, 예상됨**   
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)