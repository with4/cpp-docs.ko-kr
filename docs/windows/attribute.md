---
title: "attribute | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.attribute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__typeof keyword"
  - "custom attributes, creating"
  - "attribute attribute"
  - "attributes [C++], custom"
ms.assetid: 8cb3489f-65c4-44ea-b0aa-3c3c6b15741d
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# attribute
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자 지정 특성을 만들 수 있습니다.  
  
## 구문  
  
```  
  
      [ attribute(  
   AllowOn,  
   AllowMultiple=boolean,  
   Inherited=boolean  
) ]  
```  
  
#### 매개 변수  
 *AllowOn*  
 사용자 지정 특성을 적용할 수 있는 언어 요소를 지정 합니다.  기본값은  **System::AttributeTargets::All** \(참조 하십시오  [System::AttributeTargets](https://msdn.microsoft.com/en-us/library/system.attributetargets.aspx)\).  
  
 `AllowMultiple`  
 사용자 지정 특성을 구문에 반복적으로 적용할 수 있는지를 지정 합니다.  기본값은  **FALSE**.  
  
 `Inherited`  
 특성 클래스에 의해 상속 될 수 있는지를 나타냅니다.  컴파일러가 특별 지원을 없이이 기능을 제공합니다. 작업 특성 소비자 \(예: 리플렉션\)이이 정보를 존중 하는 것이.  경우 `Inherited` 입니다  **TRUE**, 특성이 상속 됩니다.  경우 `AllowMultiple` 입니다  **TRUE**, 특성에서 파생 된 멤버로; 누적 됩니다 경우 `AllowMultiple` 입니다  **FALSE**를 특성 재정의 \(교체에서 상속 하거나 합니다\).  경우 `Inherited` 입니다  **FALSE**에서 특성을 상속할 수 있습니다.  기본값은  **TRUE**.  
  
## 설명  
  
> [!NOTE]
>  `attribute` 특성이 더 이상 사용 되지.  공용 언어 런타임 특성을 system.attribute을 직접 사용자 정의 특성을 만들 수는 있습니다.  자세한 내용은 [User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md)를 참조하십시오.  
  
 정의  [사용자 지정 특성](../windows/custom-attributes-cpp.md) 배치 하 여는 `attribute` 특성에서 관리 되는 클래스 또는 구조체의 정의.  클래스 이름 사용자 지정 특성입니다.  예를 들면 다음과 같습니다.  
  
```  
[ attribute(Parameter) ]  
public ref class MyAttr {};  
```  
  
 함수 매개 변수를 적용할 수 있습니다 MyAttr 이라는 특성을 정의 합니다.  클래스 특성이 다른 어셈블리에서 사용 될 경우에 공용 이어야 합니다.  
  
> [!NOTE]
>  네임 스페이스 충돌을 방지 하기 위해 모든 특성 이름 암시적으로 "Attribute"로 끝나야 이 예제에서는 특성 및 클래스의 이름이 실제로 MyAttrAttribute 하지만 MyAttr 및 MyAttrAttribute 같은 의미로 사용할 수 있습니다.  
  
 명명 되지 않은 매개 변수는 특성 클래스의 public 생성자를 정의합니다.  오버 로드 된 생성자가 다음과 같은 방법으로 사용자 지정 특성에 정의의 특성을 지정 하는 여러 가지 방법으로 수행할 수 있습니다.  
  
```  
// cpp_attr_ref_attribute.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class) ]   // apply attribute to classes  
public ref class MyAttr {  
public:  
   MyAttr() {}   // Constructor with no parameters  
   MyAttr(int arg1) {}   // Constructor with one parameter  
};  
  
[MyAttr]  
ref class ClassA {};   // Attribute with no parameters  
  
[MyAttr(123)]  
ref class ClassB {};   // Attribute with one parameter  
```  
  
 클래스의 공용 데이터 멤버 및 속성은 특성의 명명 된 매개 변수 \(옵션\)입니다.  
  
```  
// cpp_attr_ref_attribute_2.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class) ]  
ref class MyAttr {  
public:  
   // Property Priority becomes attribute's named parameter Priority  
    property int Priority {  
       void set(int value) {}  
       int get() { return 0;}  
   }  
   // Data member Version becomes attribute's named parameter Version  
   int Version;  
   MyAttr() {}   // constructor with no parameters  
   MyAttr(int arg1) {}   // constructor with one parameter  
};  
  
[MyAttr(123, Version=2)]   
ref class ClassC {};  
```  
  
 가능한 특성 매개 변수 형식에 대 한 목록은  [사용자 지정 특성](../windows/custom-attributes-cpp.md).  
  
 참조 하십시오 [User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md) 토론 특성 대상에 대 한.  
  
 `attribute` 특성을 가진는 `AllowMultiple` 사용자 지정 특성을 단일 사용 되는지 여부를 지정 하는 매개 변수 또는 multiuse \(나타날 수 있습니다 두 번 이상 같은 엔터티에\).  
  
```  
// cpp_attr_ref_attribute_3.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class, AllowMultiple = true) ]  
ref struct MyAttr {  
   MyAttr(){}  
};   // MyAttr is a multiuse attribute  
  
[MyAttr, MyAttr()]  
ref class ClassA {};  
```  
  
 사용자 지정 특성 클래스는 직접 또는 간접적으로에서 파생 <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>, 빠르고 쉽게 메타 데이터에서 속성 정의 식별 하는 만듭니다.  `attribute` 특성이 명시적 파생 하지 않습니다 상속에서 System::Attribute 의미 합니다.  
  
```  
[ attribute(Class) ]  
ref class MyAttr  
```  
  
 동일한 함수는  
  
```  
[ attribute(Class) ]  
ref class MyAttr : System::Attribute   // OK, but redundant.  
```  
  
 `attribute`별칭에 대 한 <xref:System.AttributeUsageAttribute?displayProperty=fullName> \(AttributeAttribute 않습니다. 이 특성 명명 규칙의 예외입니다\).  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|`ref` **클래스**,  **ref struct**|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 예제  
  
```  
// cpp_attr_ref_attribute_4.cpp  
// compile with: /c /clr  
using namespace System;  
[attribute(AttributeTargets::Class)]  
ref struct ABC {  
   ABC(Type ^) {}  
};  
  
[ABC(String::typeid)]   // typeid operator yields System::Type ^  
ref class MyClass {};  
```  
  
## 예제  
 `Inherited` 명명 된 인수를 기본 클래스에 적용 된 사용자 지정 특성에서 파생 된 클래스의 반사 표시 됩니다 여부를 지정 합니다.  
  
```  
// cpp_attr_ref_attribute_5.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
  
[attribute( AttributeTargets::Method, Inherited=false )]  
ref class BaseOnlyAttribute { };  
  
[attribute( AttributeTargets::Method, Inherited=true )]  
ref class DerivedTooAttribute { };  
  
ref struct IBase {  
public:  
   [BaseOnly, DerivedToo]  
   virtual void meth() {}  
};  
  
// Reflection on Derived::meth will show DerivedTooAttribute   
// but not BaseOnlyAttribute.  
ref class Derived : public IBase {  
public:  
   virtual void meth() override {}  
};  
  
int main() {  
   IBase ^ pIB = gcnew Derived;  
  
   MemberInfo ^ pMI = pIB->GetType( )->GetMethod( "meth" );  
   array<Object ^> ^ pObjs = pMI->GetCustomAttributes( true );  
   Console::WriteLine( pObjs->Length ) ;  
}  
```  
  
  **2**   
## 참고 항목  
 [Attributes Alphabetical Reference](../windows/attributes-alphabetical-reference.md)   
 [Custom Attributes](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)