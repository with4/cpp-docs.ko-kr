---
title: "리플렉션(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework[C++], 리플렉션"
  - "데이터 형식[C++], 리플렉션"
  - "GetType 메서드"
  - "메타데이터, 리플렉션"
  - "리플렉션[C++}"
  - "리플렉션[C++}, 리플렉션 정보"
  - "typeid 키워드[C++]"
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 리플렉션(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

리플렉션을 사용하면 알려진 데이터 형식을 런타임에 검사할 수 있습니다.  리플렉션을 사용하면 특정 어셈블리에 있는 데이터 형식의 열거형을 사용할 수 있고 특정 클래스 또는 값 형식의 멤버를 검색할 수 있습니다.  컴파일할 때 해당 형식이 알려져 있는지 또는 참조되었는지 여부와는 상관없이 이러한 기능을 사용할 수 있습니다.  이와 같이 리플렉션은 개발 및 코드 관리 도구의 유용한 기능으로 사용됩니다.  
  
 제공된 어셈블리 이름은 어셈블리 버전, 문화권 및 서명 정보가 포함된 강력한 이름\([강력한 이름의 어셈블리](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) 참조\)입니다.  또한 데이터 형식이 정의된 네임스페이스의 이름도 기본 클래스 이름과 함께 검색할 수 있습니다.  
  
 리플렉션 기능에 액세스하는 가장 일반적인 방법은 <xref:System.Object.GetType%2A> 메서드를 사용하는 것입니다.  이 메서드는 모든 가비지 수집 클래스를 파생시키는 [System::Object](https://msdn.microsoft.com/en-us/library/system.object.aspx)에서 제공합니다.  
  
 Visual C\+\+ 컴파일러를 사용하여 빌드한 .exe에 대해 리플렉션을 사용하려면 .exe를 빌드할 때 **\/clr:pure** 또는 **\/clr:safe** 컴파일러 옵션을 사용했어야 합니다.  자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)를 참조하십시오.  
  
 이 단원의 항목:  
  
-   [방법: 리플렉션을 사용하여 플러그 인 구성 요소 아키텍처 구현](../dotnet/how-to-implement-a-plug-in-component-architecture-using-reflection-cpp-cli.md)  
  
-   [방법: 리플렉션을 사용하여 어셈블리에 데이터 형식 열거](../dotnet/how-to-enumerate-data-types-in-assemblies-using-reflection-cpp-cli.md)  
  
 자세한 내용은 [System.Threading 네임스페이스](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)를 참조하십시오.  
  
## 예제  
 `GetType` 메서드는 해당 개체의 기본 형식을 나타내는 <xref:System.Type> 클래스 개체에 대한 포인터를 반환합니다. **Type** 개체는 인스턴스 관련 정보를 포함하지 않습니다. 다음과 같이 형식의 전체 이름이 포인터로 반환될 수 있습니다.  
  
 형식 이름에는 네임스페이스를 비롯하여 해당 형식이 정의된 전체 범위가 포함되어 있습니다. 형식 이름은 점을 범위 확인 연산자로 사용하여 .NET 구문으로 표시됩니다.  
  
```  
// vcpp_reflection.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^ s = "sample string";  
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());  
}  
```  
  
  **'sample string'의 전체 형식 이름은 'System.String'**   
## 예제  
 값 형식을 `GetType` 함수에 사용할 수도 있지만 이 경우에는 먼저 boxing되어야 합니다.  
  
```  
// vcpp_reflection_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Int32 i = 100;   
   Object ^ o = i;  
   Console::WriteLine("type of i = '{0}'", o->GetType());  
}  
```  
  
  **i 형식 \= 'System.Int32'**   
## 예제  
 `GetType` 메서드와 마찬가지로 [typeid](../windows/typeid-cpp-component-extensions.md) 연산자는 **Type** 개체에 대한 포인터를 반환하므로 이 코드는 형식 이름 **System.Int32**를 나타냅니다.  형식 이름을 표시하는 것은 리플렉션의 가장 기본적인 기능이지만 열거형 형식에 대한 유효한 값을 검사하거나 검색하는 등과 같이 더 유용한 기능도 활용할 수 있습니다.  정적 **Enum::GetNames** 함수를 사용하면 이러한 작업을 수행할 수 있습니다. 이 함수는 문자열 배열을 반환하며 이 배열의 각 문자열에는 텍스트 형식의 열거형 값이 포함되어 있습니다.  다음 샘플에서는 **Options**\(CLR\) 열거형의 열거형 값을 나타내는 문자열 배열을 검색하고 루프에 이를 표시합니다.  
  
 **Options** 열거형에 네 번째 옵션이 추가될 경우 해당 열거형이 다른 어셈블리에 정의되어 있더라도 이 코드는 다시 컴파일하지 않고 새 옵션을 보고합니다.  
  
```  
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
  
  **열거형 'Options'에 세 가지 옵션이 있음**  
**0: 옵션1**  
**1: 옵션2**  
**2: 옵션 3**  
**'o'의 값은 Option2입니다.**   
## 예제  
 `GetType` 개체는 형식을 검사하는 데 사용할 수 있는 다양한 멤버와 속성을 지원합니다.  다음 코드에서는 이러한 정보 중 몇 가지를 검색하고 표시합니다.  
  
```  
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
  
  **'String'에 대한 정보 입력:**  
**어셈블리 이름: mscorlib, 버전\=1.0.5000.0, Culture\=neutral,**   
**PublicKeyToken\=b77a5c561934e089**  
**네임스페이스: System**  
**기본 형식은 System.Object입니다.**  
**배열: False**  
**클래스: True**   
## 예제  
 리플렉션을 사용하면 어셈블리 내에 형식 열거형을 두거나 클래스 내에 멤버를 둘 수 있습니다.  이 기능을 보여 주기 위해 다음과 같이 간단한 클래스를 정의합니다.  
  
```  
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
  
## 예제  
 위 코드가 vcpp\_reflection\_6.dll이라는 DLL로 컴파일되면 리플렉션을 사용하여 이 어셈블리의 내용을 검사할 수 있습니다.  여기에는 정적 리플렉션 API 함수 [Assembly::Load](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx)를 사용하여 어셈블리를 로드하는 것도 포함됩니다.  이 함수는 **Assembly** 개체의 주소를 반환하므로 이 개체 내에서 모듈 및 형식에 대한 정보를 쿼리할 수 있습니다.  
  
 리플렉션 시스템에서 어셈블리를 로드하고 나면 [Assembly::GetTypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx) 함수를 통해 **Type** 개체 배열이 검색됩니다.  각 배열 요소에는 서로 다른 형식에 대한 정보가 포함되어 있지만 여기에서는 하나의 클래스만 정의되어 있습니다.  루프에서 **Type::GetMembers** 함수를 사용하여 이 배열의 각 **Type**에 대해 형식 멤버를 쿼리할 수 있습니다.  이 함수는 **MethodInfo** 개체의 배열을 반환하는데, 각 개체에는 해당 형식의 멤버 함수, 데이터 멤버 또는 속성 정보에 대한 정보가 들어 있습니다.  
  
 메서드 목록에는 **TestClass**에 명시적으로 정의된 함수와 **System::Object** 클래스에서 암시적으로 상속된 함수가 포함되어 있습니다.  Visual C\+\+ 구문 대신 .NET으로 표현될 때 속성은 get\/set 함수에 의해 액세스되는 내부 데이터 멤버로 나타납니다.  get\/set 함수는 이 목록에 정규 메서드로 나타납니다.  리플렉션은 Visual C\+\+ 컴파일러가 아니라 공용 언어 런타임을 통해 지원됩니다.  
  
 여기에서는 정의한 어셈블리를 검사하는 데 이 코드를 사용했지만 이 코드로 .NET 어셈블리를 검사할 수도 있습니다.  예를 들어, TestAssembly를 mscorlib로 변경하면 mscorlib.dll에 정의된 모든 형식 및 메서드 목록을 볼 수 있습니다.  
  
```  
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
  
## 참고 항목  
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)