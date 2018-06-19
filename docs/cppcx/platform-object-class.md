---
title: 'Platform:: object 클래스 | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Object::Object
- VCCORLIB/Platform::Object::Equals
- VCCORLIB/Platform::Object::GetHashCode
- VCCORLIB/Platform::Object::ReferenceEquals
- VCCORLIB/Platform::ToString
- VCCORLIB/Platform::GetType
dev_langs:
- C++
helpviewer_keywords:
- Object class
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a7fc6dc1df1d1e22032dbe7322b9a6ead8334ddc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091883"
---
# <a name="platformobject-class"></a>Platform::Object 클래스
Ref 클래스 및 ref 구조체는 Windows 런타임 앱에 대 한 일반적인 동작을 제공 합니다. 모든 ref 클래스 및 ref 구조체 인스턴스는 Platform::Object^로 암시적으로 변환될 수 있고 해당하는 가상 ToString 메서드를 재정의할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
public ref class Object : Object  
```  
  
### <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Object::Object](#ctor)|Object 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Object::Equals](#equals)|지정한 개체와 현재 개체가 같은지 여부를 확인합니다.|  
|[Object::GetHashCode](#gethashcode)|이 인스턴스의 해시 코드를 반환합니다.|  
|[Object::ReferenceEquals](#referenceequals)|지정한 Object 인스턴스가 동일한지 여부를 확인합니다.|  
|[ToString](#tostring)|현재 개체를 나타내는 문자열을 반환합니다. 재정의될 수 있습니다.|  
|[GetType](#gettype)|현재 인스턴스를 설명하는 [Platform::Type](../cppcx/platform-type-class.md) 을 가져옵니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Object`  
  
 `Object`  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** vccorlib.h  
  
 **네임스페이스:** Platform  

  
## <a name="equals"></a> Object:: equals 메서드
지정한 개체와 현재 개체가 같은지 여부를 확인합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
bool Equals(  
    Object^ obj  
)  
```  
  
### <a name="parameters"></a>매개 변수  
 obj  
 비교할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 개체가 동일하면`true` 이고, 그렇지 않으면 `false`입니다.  
  


## <a name="gethashcode"></a>  Object:: gethashcode 메서드
COM 개체인 경우 이 인스턴스에 대한 `IUnknown`* ID 값을 반환하고, COM 개체가 아닌 경우 계산된 해시 값을 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>반환 값  
 이 개체를 고유하게 식별하는 숫자 값입니다.  
  
### <a name="remarks"></a>설명  
 GetHashCode를 사용하여 맵에 개체의 키를 만들 수 있습니다. 사용 하 여 해시 코드를 비교할 수 [object:: equals](#equals)합니다. 코드 경로가 매우 중요하며 `GetHashCode` 및 `Equals`가 충분히 빠르지 않은 경우 기본 COM 레이어로 드롭다운하고 네이티브 `IUnknown` 포인터 비교를 수행할 수 있습니다.  
  


## <a name="gettype"></a>  Object:: gettype 메서드
반환 된 [platform:: type](../cppcx/platform-type-class.md) 개체의 런타임 형식을 설명 하는 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
Object::GetType()  
```  

  
### <a name="property-valuereturn-value"></a>속성 값/반환 값  
 A [platform:: type](../cppcx/platform-type-class.md) 개체의 런타임 형식을 설명 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 정적 [type:: gettypecode](../cppcx/platform-type-class.md#gettypecode) 가져오는 데 사용할 수는 [platform:: typecode 열거형](../cppcx/platform-typecode-enumeration.md) 현재 형식을 나타내는 값입니다. 대부분의 경우 이는 기본 제공 형식에 유용합니다. 제외한 모든 ref 클래스에 대 한 형식 코드 [platform:: string](../cppcx/platform-string-class.md) 개체 (1)입니다.  
  
 [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) 클래스 Windows 구성 요소와 앱 간에 형식 정보를 전달 하는 언어 독립적 방법으로 Windows Api에서 사용 됩니다. T[platform:: type 클래스](../cppcx/platform-type-class.md) 형식 사이의 변환 하기 위한 연산자가 `Type` 및 `TypeName`합니다.  
  
 사용 하 여 [typeid](../windows/typeid-cpp-component-extensions.md) 반환 하도록 연산자는 `Platform::Type` 하면 XAML 페이지 간을 탐색할 때 등에 클래스 이름에 대 한 개체:  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## <a name="see-also"></a>참고 항목  
 [Platform:: type 클래스](../cppcx/platform-type-class.md)   
 [Platform 네임 스페이스](../cppcx/platform-namespace-c-cx.md)   
 [Type System](../cppcx/type-system-c-cx.md
  
## <a name="ctor"></a>  Object:: object 생성자
Object 클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
public:Object()  
```  

## <a name="referenceequals"></a>  Object:: referenceequals 메서드
지정한 Object 인스턴스가 동일한지 여부를 확인합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
public:static bool ReferenceEquals(  Object^ obj1,   Object^ obj2)  
```  
  
### <a name="parameters"></a>매개 변수  
 obj1  
 비교할 첫 번째 개체입니다.  
  
 obj2  
 비교할 두 번째 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 두 개체가 같으면 `true`이고, 그렇지 않으면 `false`입니다.  
 
## <a name="tostring"></a>  Object:: tostring 메서드 (C + + /cli CX)
현재 개체를 나타내는 문자열을 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
public:  
virtual String^ ToString()  
```  
  
### <a name="return-value"></a>반환 값  
 현재 개체를 나타내는 문자열입니다. 이 메서드를 재정의하여 ref 클래스 또는 구조체에서 사용자 지정 문자열 메시지를 제공할 수 있습니다.  
  
```cpp  
public ref class Tree sealed  
{  
public:  
    Tree(){}  
    virtual Platform::String^ ToString() override  
    {  
      return "I’m a Tree";  
    };  
};  
```  
## <a name="see-also"></a>참고 항목  
 [플랫폼 Namespace](platform-namespace-c-cx.md)