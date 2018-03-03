---
title: "typeid (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- typeid keyword [C++]
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 20a3b1153bbb8a8502a54aa74998817abf191860
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="typeid--c-component-extensions"></a>typeid(C++ 구성 요소 확장)
개체의 유형을 나타내는 값을 가져옵니다.  
  
> [!WARNING]
>  이 항목은 TypeId의 C++ 구성 요소 확장명 버전을 참조합니다. 이 키워드는 ISO c + + 버전에서는 참조 [typeid 연산자](../cpp/typeid-operator.md)합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
  
### <a name="syntax"></a>구문  
  
```cpp  
T::typeid  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 형식 이름.  
  
## <a name="windows-runtime"></a>Windows 런타임  
  
### <a name="syntax"></a>구문  
  
```cpp  
Platform::Type^ type = T::typeid;  
```  
  
### <a name="parameters"></a>매개 변수  
 `T`  
 형식 이름.  
  
### <a name="remarks"></a>설명  
 C + + /CX에서는 typeid 반환는 [platform:: type](../cppcx/platform-type-class.md) 런타임 형식 정보에서 생성 되는 합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 **구문**  
  
```  
  
type::typeid  
```  
  
 **매개 변수**  
  
 *type*  
 형식 (추상 선언 자)을 system:: type 개체의 이름입니다.  
  
 **주의**  
  
 `typeid`얻는 데 사용 되는 <xref:System.Type> 컴파일 시 형식에 대 한 합니다.  
  
 `typeid`사용 하 여 런타임에 형식에 대 한 고:: type을 가져오는 것과 비슷합니다 <xref:System.Type.GetType%2A> 또는 <xref:System.Object.GetType%2A>합니다. 그러나 typeid 허용 된 형식 이름을 매개 변수로 합니다.  System:: type 이름을 가져올 형식의 인스턴스를 사용 하려는 경우 GetType를 사용 합니다.  
  
 `typeid`GetType 실행 시 반환할 유형을 평가 하는 반면 컴파일 타임에 형식 이름 (형식)를 계산할 할 수 있어야 합니다.  
  
 `typeid`네이티브 형식 이름 또는 네이티브 형식 name;에 대 한 공용 언어 런타임 별칭 걸릴 수 있습니다. 참조 [c + + 네이티브 형식에 해당 하는.NET Framework (C + + /cli CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md) 자세한 정보에 대 한 합니다.  
  
 `typeid`네이티브 형식에서 작동도 있지만 여전히는 system:: type을 반환 합니다.  Type_info 구조를 가져오려면 [typeid 연산자](../cpp/typeid-operator.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 예제에서는 typeid 키워드 gettype () 멤버를 비교합니다.  
  
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
  
 **출력**  
  
```Output  
typeid and GetType returned the same System::Type  
G  
  
System.Single*  
  
```  
  
 **예제**  
  
 다음 샘플:: type 형식에 특성을 가져오는 데 사용할 수는 형식의 변수에 보여 줍니다.  또한 일부 형식의 해야 합니다를 사용 하도록 형식 정의 만들려면 표시 `typeid`합니다.  
  
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
  
 **출력**  
  
```Output  
True  
  
in AtClass2 constructor  
  
in AtClass Type ^ constructor  
  
AtClass2  
  
System.AttributeUsageAttribute  
  
AtClass  
  
int::typeid != pointer_to_int::typeid, as expected  
  
int::typeid == handle_to_int::typeid, as expected  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)