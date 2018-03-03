---
title: "특성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 42ea9049fdd97691bd139599705856baa8acfee1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
 사용자 지정 특성 적용 될 수 있는 언어 요소를 지정 합니다. 기본값은 **System::AttributeTargets::All** (참조 [System::AttributeTargets](https://msdn.microsoft.com/en-us/library/system.attributetargets.aspx)).  
  
 `AllowMultiple`  
 구문에 사용자 지정 특성 반복적으로 적용 될 수 있는지 여부를 지정 합니다. 기본값은 **FALSE**합니다.  
  
 `Inherited`  
 서브 클래스에서 상속 하는 특성 인지 여부를 나타냅니다. 컴파일러는이 기능은;는 특별 한 지원 하지 않습니다. 것은이 정보를 고려 하는 특성 소비자 (예: 리플렉션) 작업입니다. 경우 `Inherited` 은 **TRUE**, 특성이 상속 됩니다. 경우 `AllowMultiple` 은 **TRUE**, 특성 서버에 누적 되며 파생된 멤버가; 경우 `AllowMultiple` 은 **FALSE**, 특성은 재정의 (또는 바꾸기) 상속에서 합니다. 경우 `Inherited` 은 **FALSE**, 특성은 상속 되지 않습니다. 기본값은 **TRUE**합니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  `attribute` 특성은 이제 사용 되지 않습니다.  사용자 정의 특성을 만들려면 공용 언어 런타임 특성 System.Attribute 직접를 사용 합니다.  자세한 내용은 참조 [사용자 정의 특성](../windows/user-defined-attributes-cpp-component-extensions.md)합니다.  
  
 정의 하는 [사용자 지정 특성](../windows/custom-attributes-cpp.md) 배치 하 여는 `attribute` 관리 되는 클래스 또는 구조체 정의에 특성입니다. 클래스의 이름에는 사용자 지정 특성입니다. 예:  
  
```  
[ attribute(Parameter) ]  
public ref class MyAttr {};  
```  
  
 함수 매개 변수에 적용할 수 있는 MyAttr 라는 특성을 정의 합니다. 클래스 특성은 다른 어셈블리에서 사용 하려는 경우에 공용 이어야 합니다.  
  
> [!NOTE]
>  네임 스페이스 충돌을 방지 하려면 모든 특성 이름이 암시적으로 끝나야 "특성"; 이 예제에서는 특성 및 클래스 이름은 실제로 MyAttrAttribute 하지만 MyAttr 및 MyAttrAttribute 교대로 사용할 수 있습니다.  
  
 클래스의 public 생성자는 특성의 명명 되지 않은 매개 변수를 정의합니다. 오버 로드 된 생성자 허용 되는 사용자 지정 특성에는 다음과 같은 방법으로 정의 된 특성을 지정 하는 여러 방법을:  
  
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
  
 클래스의 공용 데이터 멤버 및 속성은 특성의 명명 된 매개 변수 (옵션):  
  
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
  
 목록이 가능한 특성 매개 변수 형식에 대 한 참조 [사용자 정의 특성](../windows/custom-attributes-cpp.md)합니다.  
  
 참조 [사용자 정의 특성](../windows/user-defined-attributes-cpp-component-extensions.md) 특성 대상에 대 한 내용은 합니다.  
  
 `attribute` 특성에는 `AllowMultiple` 사용자 지정 특성의 단일 사용 여부를 지정 하는 매개 변수 또는 multiuse (에 표시할 수 두 번 이상 같은 엔터티)입니다.  
  
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
  
 사용자 지정 특성 클래스에 직접 또는 간접적으로에서 파생 됩니다 <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>를 식별 하는 빠르고 쉬운 메타 데이터의 특성 정의가 있습니다. `attribute` 내재 하 고 system:: attribute에서 상속 하므로 명시적 파생 필요 하지 않습니다.  
  
```  
[ attribute(Class) ]  
ref class MyAttr  
```  
  
 위의 식은 아래의 식과 동일합니다.  
  
```  
[ attribute(Class) ]  
ref class MyAttr : System::Attribute   // OK, but redundant.  
```  
  
 `attribute`에 대 한 별칭은 <xref:System.AttributeUsageAttribute?displayProperty=fullName> (AttributeAttribute 하지 않으면 특성 명명 규칙에 대 한 예외입니다).  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|`ref`**클래스**, **ref 구조체**|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="example"></a>예  
  
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
  
## <a name="example"></a>예  
 `Inherited` 명명 된 인수는 기본 클래스에 적용 하는 사용자 지정 특성의 파생된 클래스는 리플렉션에 표시 됩니다 있는지 여부를 지정 합니다.  
  
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
  
```Output  
2  
```  
  
## <a name="see-also"></a>참고 항목  
 [특성 사전순 참조](../windows/attributes-alphabetical-reference.md)   
 [사용자 지정 특성](http://msdn.microsoft.com/en-us/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)