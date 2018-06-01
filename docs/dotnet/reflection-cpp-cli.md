---
title: 리플렉션 (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d41d7f627a50dd1a09f4256fbd8448d82c6d5f27
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705246"
---
# <a name="reflection-ccli"></a>리플렉션(C++/CLI)

리플렉션 알려진된 데이터 형식은 런타임에 검사할 수 있습니다. 리플렉션이 특정된 어셈블리에 있는 데이터 형식의 열거형을 사용 하면 및 지정 된 클래스 또는 값 형식의 멤버를 검색할 수 있습니다. 형식을 알 수 없거나 컴파일 타임에 참조 된 여부에 관계 없이 유용 합니다. 이렇게 하면 리플렉션 개발 및 코드 관리 도구에 대 한 유용한 기능입니다.

제공 된 어셈블리 이름은 강력한 이름 (참조 [and using strong-named Assemblies](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)), 어셈블리 버전, 문화권 및 서명 정보를 포함 하 합니다. 또한 note 하 데이터 형식이 정의 되어 있는 네임 스페이스 이름을 검색할 수 있습니다, 기본 클래스의 이름과 함께 합니다.

리플렉션 기능에 액세스 하는 가장 일반적인 방법은 방식은 <xref:System.Object.GetType%2A> 메서드. 이 메서드는 제공한 [system:: object](https://msdn.microsoft.com/en-us/library/system.object.aspx)에서 가비지 수집 된 모든 클래스를 파생 합니다.

> [!NOTE]
> Visual c + + 컴파일러를 사용 하 여 빌드한.exe에 대 한 리플렉션이.exe로 작성 하는 경우에 허용 됩니다는 **/clr: pure** 또는 **/clr: safe** 컴파일러 옵션입니다. **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않는 및 Visual Studio 2017에 사용할 수 없습니다. 참조 [/clr (공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md) 자세한 정보에 대 한 합니다.

자세한 내용은 참조 [System.Reflection Namespace](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)

## <a name="example-gettype"></a>예: GetType

`GetType` 에 대 한 포인터를 반환 하는 메서드는 <xref:System.Type> 클래스 개체에는 개체를 기반으로 하는 경우에 형식에 설명 합니다. (의 **형식** 개체는 인스턴스 관련 정보를 포함 하지 않습니다.) 이러한 항목은 다음과 같이 표시 될 수 있는 형식의 전체 이름:

형식 이름 형식을 정의 되어 있는, 네임 스페이스를 포함 하 여 전체 범위를 포함 하 고 범위 확인 연산자도 점이 있는.NET 구문에서 표시 되는 참고 합니다.

```cpp
// vcpp_reflection.cpp
// compile with: /clr
using namespace System;
int main() {
   String ^ s = "sample string";
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());
}
```

```Output
full type name of 'sample string' is 'System.String'
```

## <a name="example-boxed-value-types"></a>예제: boxed 값 형식

값 형식에 사용할 수는 `GetType` 에서도 작동 하지만 먼저 boxed 수 있어야 합니다.

```cpp
// vcpp_reflection_2.cpp
// compile with: /clr
using namespace System;
int main() {
   Int32 i = 100; 
   Object ^ o = i;
   Console::WriteLine("type of i = '{0}'", o->GetType());
}
```

```Output
type of i = 'System.Int32'
```

## <a name="example-typeid"></a>예: typeid

와 마찬가지로 `GetType` 메서드는 [typeid](../windows/typeid-cpp-component-extensions.md) 연산자에 대 한 포인터를 반환 합니다.는 **형식** 개체,이 코드는 유형 이름을 나타냅니다 **System.Int32**합니다. 형식 이름 표시 리플렉션의 가장 기본적인 기능 않으며 더 유용한 방법은 검사 하거나 열거 형식에 대 한 유효한 값을 검색 하는 것입니다. 정적을 사용 하 여이 작업을 수행할 수 있습니다 **Enum::GetNames** 함수를 반환 하는 문자열의 배열을 각각은 텍스트 형식에서 열거형 값을 포함 합니다.  다음 샘플에 대 한 열거형 값에 설명 하는 문자열의 배열을 검색는 **옵션** (CLR) 열거형 루프에 표시 됩니다.

네 번째 옵션에 추가 되 면는 **옵션** 열거형이이 코드는 열거형은 별도 어셈블리에 정의 되어 있는 경우에 다시 컴파일하지 않고 새로운 옵션을 보고 합니다.

```cpp
// vcpp_reflection_3.cpp
// compile with: /clr
using namespace System;

enum class Options {   // not a native enum
   Option1, Option2, Option3
};

int main() {
   array<String^>^ names = Enum::GetNames(Options::typeid);

   Console::WriteLine("there are {0} options in enum '{1}'", 
               names->Length, Options::typeid);

   for (int i = 0 ; i < names->Length ; i++)
      Console::WriteLine("{0}: {1}", i, names[i]);

   Options o = Options::Option2;
   Console::WriteLine("value of 'o' is {0}", o);
}
```

```Output
there are 3 options in enum 'Options'
0: Option1
1: Option2
2: Option3
value of 'o' is Option2
```

## <a name="example-gettype-members-and-properties"></a>예: GetType 멤버 및 속성

`GetType` 개체가 다양 한 멤버와는 형식을 검사 하는 데 사용할 수 있는 속성을 지원 합니다. 이 코드를 검색 하 고이 정보 중 일부가 표시 됩니다.

```cpp
// vcpp_reflection_4.cpp
// compile with: /clr
using namespace System;
int main() {
   Console::WriteLine("type information for 'String':");
   Type ^ t = String::typeid;

   String ^ assemblyName = t->Assembly->FullName;
   Console::WriteLine("assembly name: {0}", assemblyName);

   String ^ nameSpace = t->Namespace;
   Console::WriteLine("namespace: {0}", nameSpace);

   String ^ baseType = t->BaseType->FullName;
   Console::WriteLine("base type: {0}", baseType);

   bool isArray = t->IsArray;
   Console::WriteLine("is array: {0}", isArray);

   bool isClass = t->IsClass;
   Console::WriteLine("is class: {0}", isClass);
}
```

```Output
type information for 'String':
assembly name: mscorlib, Version=1.0.5000.0, Culture=neutral, 
PublicKeyToken=b77a5c561934e089
namespace: System
base type: System.Object
is array: False
is class: True
```

## <a name="example-enumeration-of-types"></a>예: 열거형 형식

리플렉션에는 어셈블리 내에서 형식 및 클래스 내에서 멤버를 열거할 수 있습니다. 이 기능을 보여 주기 위해 간단한 클래스를 정의 합니다.

```cpp
// vcpp_reflection_5.cpp
// compile with: /clr /LD
using namespace System;
public ref class TestClass {
   int m_i;
public:
   TestClass() {}
   void SimpleTestMember1() {}
   String ^ SimpleMember2(String ^ s) { return s; } 
   int TestMember(int i) { return i; }
   property int Member {
      int get() { return m_i; }
      void set(int i) { m_i = i; }
   }
};
```

## <a name="example-inspection-of-assemblies"></a>어셈블리의 예: 검사

위의 코드 vcpp_reflection_6.dll를 호출 하는 DLL로 컴파일될 경우이 어셈블리의 내용을 확인 하려면 다음 리플렉션을 사용할 수 있습니다. 정적 리플렉션 API 함수를 사용 하는 것이 [Assembly::Load](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx) 어셈블리를 로드 합니다. 주소를 반환 하는이 함수는 **어셈블리** 모듈 및 내의 형식에 대 한 다음 쿼리할 수 있는 개체입니다.

리플렉션 시스템 어셈블리의 배열에서 성공적으로 로드 되 면 **형식** 개체와 함께 검색 되는 [Assembly::GetTypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx) 함수입니다. 이 경우 클래스를 하나만 정의 하지만 다른 형식에 대 한 정보를 포함 하는 각 배열 요소 합니다. 루프를 사용 하 여 각 **형식** 이 배열에 사용 하 여 형식 멤버에 대 한 쿼리는 **Type::GetMembers** 함수입니다. 이 함수는의 배열을 반환 **MethodInfo** 개체, 각 개체에 멤버 함수, 데이터 멤버 또는 형식의 속성에에서 대 한 정보가 들어 있는입니다.

에 정의 된 방법 목록에는 함수를 명시적으로 포함 하는 참고 **TestClass** 에서 암시적으로 상속 된 함수는 **system:: object** 클래스입니다. Visual c + + 구문에서 하지 않고.NET에서 설명 하 고의 일환으로, get/set 함수에서 액세스 하는 기본 데이터 멤버와 속성이 표시 됩니다. Get/set 함수로 정규 메서드로이 목록에 나타납니다. Visual c + + 컴파일러가 아닌 공용 언어 런타임을 통해 리플렉션은 지원 됩니다.

정의 된 어셈블리를 검사 하려면이 코드를 사용 해도.NET 어셈블리를 검사 하 또한이 코드를 사용할 수 있습니다. 예를 들어 TestAssembly에는 mscorlib에 변경 하면 모든 형식과 mscorlib.dll에 정의 된 메서드 목록이 표시 됩니다.

```cpp
// vcpp_reflection_6.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;
using namespace System::Reflection;
int main() {
   Assembly ^ a = nullptr;
   try {
      // load assembly -- do not use file extension
      // will look for .dll extension first
      // then .exe with the filename
      a = Assembly::Load("vcpp_reflection_5");
   }
   catch (FileNotFoundException ^ e) {
      Console::WriteLine(e->Message);
      return -1;
   }

   Console::WriteLine("assembly info:");
   Console::WriteLine(a->FullName);
   array<Type^>^ typeArray = a->GetTypes();

   Console::WriteLine("type info ({0} types):", typeArray->Length);

   int totalTypes = 0;
   int totalMembers = 0;
   for (int i = 0 ; i < typeArray->Length ; i++) {
      // retrieve array of member descriptions
      array<MemberInfo^>^ member = typeArray[i]->GetMembers();

      Console::WriteLine("  members of {0} ({1} members):", 
      typeArray[i]->FullName, member->Length);
      for (int j = 0 ; j < member->Length ; j++) {
         Console::Write("       ({0})", 
         member[j]->MemberType.ToString() );
         Console::Write("{0}  ", member[j]);
         Console::WriteLine("");
         totalMembers++;
      }
      totalTypes++;
   }
   Console::WriteLine("{0} total types, {1} total members",
   totalTypes, totalMembers);
}
```

## <a name="see-also"></a>참고자료

- [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
