---
title: 특성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.attribute
dev_langs:
- C++
helpviewer_keywords:
- __typeof keyword
- custom attributes, creating
- attribute attribute
- attributes [C++], custom
ms.assetid: 8cb3489f-65c4-44ea-b0aa-3c3c6b15741d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d72506e3f384a784bce4d159e8e76e88098c79f7
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461811"
---
# <a name="attribute"></a>특성
사용자 지정 특성을 만들 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ attribute(  
   AllowOn,  
   AllowMultiple=boolean,  
   Inherited=boolean  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *AllowOn*  
 사용자 지정 특성 적용 될 수 있는 언어 요소를 지정 합니다. 기본값은 `System::AttributeTargets::All` (참조 [System::AttributeTargets](https://msdn.microsoft.com/library/system.attributetargets.aspx)).  
  
 *AllowMultiple*  
 구문에 사용자 지정 특성 반복적으로 적용 될 수 있는지 여부를 지정 합니다. 기본값은 FALSE입니다.  
  
 *상속*  
 서브 클래스에서 상속 될 특성 인지 여부를 나타냅니다. 컴파일러에서이 기능에 대 한 없는 특별 한 지원을 제공합니다 이 정보를 존중 하는 특성 소비자 (예: 리플렉션) 작업 것입니다. 하는 경우 *상속 된 항목* 가 TRUE 이면 특성 상속 됩니다. 하는 경우 *AllowMultiple* 가 TRUE 인 경우 특성 파생된 멤버는;에 누적 됩니다 *AllowMultiple* 은 FALSE 특성은 재정의 (또는 바꾸기) 상속에서 합니다. 하는 경우 *상속 된 항목* 은 FALSE 특성은 상속 되지 않습니다. 기본값은 TRUE입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  `attribute` 특성은 이제 사용 되지 않습니다.  공용 언어 런타임 특성 System.Attribute 직접 사용자 정의 특성을 만들려면 사용 합니다.  자세한 내용은 [사용자 정의 특성](../windows/user-defined-attributes-cpp-component-extensions.md)합니다.  
  
 정의 하는 [사용자 지정 특성](../windows/custom-attributes-cpp.md) 배치 하 여는 `attribute` 관리 되는 클래스 또는 구조체 정의 특성으로 합니다. 클래스의 이름을 사용자 지정 특성입니다. 예를 들어:  
  
```  
[ attribute(Parameter) ]  
public ref class MyAttr {};  
```  
  
 호출 특성을 정의 `MyAttr` 함수 매개 변수를 적용할 수 있습니다. 클래스 특성은 다른 어셈블리에서 사용할 예정인 경우에 public 이어야 합니다.  
  
> [!NOTE]
>  네임 스페이스 충돌을 방지 하려면 모든 특성 이름은 암시적으로 끝나야 "특성"; 이 예제에서는 특성 및 클래스 이름은 실제로 `MyAttrAttribute`, 하지만 `MyAttr` 고 `MyAttrAttribute` 서로 교환해 서 사용할 수 있습니다.  
  
 클래스의 public 생성자는 특성의 명명 되지 않은 매개 변수를 정의합니다. 여러 가지 방법을 사용 하는 사용자 지정 특성을 다음과 같이 정의 된 특성을 지정 하는 오버 로드 된 생성자를 통해:  
  
```cpp  
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
  
 클래스의 공용 데이터 멤버 및 속성은 특성의 선택적 명명 된 매개 변수:  
  
```cpp  
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
  
 가능한 특성 매개 변수 형식의 목록, 참조 [사용자 지정 특성](../windows/custom-attributes-cpp.md)합니다.  
  
 참조 [사용자 정의 특성](../windows/user-defined-attributes-cpp-component-extensions.md) 특성 대상에 대 한 논의 합니다.  
  
 합니다 `attribute` 특성에는 *AllowMultiple* 사용자 지정 특성은 단일 사용 여부를 지정 하는 매개 변수 또는 multiuse (나타날 수 있음 두 번 이상 동일한 엔터티에).  
  
```cpp  
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
  
 사용자 지정 특성 클래스에 직접 또는 간접적으로에서 파생 됩니다 <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>를 쉽고 빠르게 메타 데이터에서 특성 정의 식별할 수 있도록 하는 합니다. `attribute` 특성 의미 system:: attribute에서 상속 하므로 명시적 파생 하지 않아도 됩니다.  
  
```  
[ attribute(Class) ]  
ref class MyAttr  
```  
  
 위의 식은 아래의 식과 동일합니다.  
  
```  
[ attribute(Class) ]  
ref class MyAttr : System::Attribute   // OK, but redundant.  
```  
  
 `attribute` 에 대 한 별칭인 <xref:System.AttributeUsageAttribute?displayProperty=fullName> (있지 AttributeAttribute; 특성 명명 규칙에 대 한 예외입니다).  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**ref 클래스**, **ref 구조체**|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="example"></a>예  
  
```cpp  
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
  
## <a name="example"></a>예  
 `Inherited` 명명 된 인수는 기본 클래스에 적용 된 사용자 지정 특성을 파생된 클래스의 리플렉션에 표시 됩니다 있는지 여부를 지정 합니다.  
  
```cpp  
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
  
```Output  
2  
```  
  
## <a name="see-also"></a>참고 항목  
 [특성 사전순 참조](../windows/attributes-alphabetical-reference.md)   
 [사용자 지정 특성](http://msdn.microsoft.com/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)