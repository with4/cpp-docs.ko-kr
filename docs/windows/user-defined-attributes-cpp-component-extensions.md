---
title: "User-Defined Attributes  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "metadata, extending"
  - "custom attributes, extending metadata"
ms.assetid: 98b29048-a3ea-4698-8441-f149cdaec9fb
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# User-Defined Attributes  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자 지정 특성을 사용하여 인터페이스, 클래스 또는 구조체, 메서드, 매개 변수 또는 열거형의 메타 데이터를 확장할 수 있습니다.  
  
## 모든 런타임  
 모든 런타임 사용자 지정 특성을 지원합니다.  
  
## Windows 런타임\(Windows Runtime\)  
 C \+ \+ \/ CX 속성은 속성 만 지원하지만, 생성자 또는 메소드 속성은 없습니다.  
  
### 설명  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## 공용 언어 런타임  
 사용자 지정 특성은 관리되는 요소의 메타 데이터를 확장 할 수 있습니다.  자세한 내용은 [특성](../Topic/Extending%20Metadata%20Using%20Attributes.md)을 참조하십시오.  
  
### 설명  
 이 항목에 제시된 정보와 구문은 [attribute](../windows/attribute.md)에 표시되는 정보를 대체하기위한 것입니다.  
  
 해당 형식에 대한<xref:System.Attribute> 기본 클래스를 생성하거나 선택적으로 <xref:System.AttributeUsageAttribute> 특성을 적용하여 사용자 지정 특성을 정의할 수 있습니다.  
  
 예를 들어, Microsoft 트랜잭션 서버 \(MTS\) 1.0, 등 거래와 관련, 동기화,로드 밸런싱 및과 동작은 ODL 사용자 지정 특성을 사용하여 형식 라이브러리에 삽입 된 사용자 지정 GUID를 통해 지정되었습니다.  따라서, MTS 서버의 클라이언트 형식 라이브러리를 읽어 그 특성을 결정할 수 있습니다.  . NET Framework의 형식 라이브러리의 아날로그 메타 데이터, 그리고 ODL 사용자 지정 특성의 아날로그 사용자 정의 속성입니다.  또한, 형식 라이브러리를 읽는 것은 형식에 리플렉션을 사용하는 것과 유사합니다.  
  
 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [Attribute Targets](../windows/attribute-targets-cpp-component-extensions.md)  
  
-   [Attribute Parameter Types](../windows/attribute-parameter-types-cpp-component-extensions.md)  
  
 Visual C\+\+의 어셈블리 서명에 대한 내용은 [강력한 이름 어셈블리\(어셈블리 서명\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)를 참조하십시오.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 샘플에서는 사용자 지정 특성을 정의하는 방법을 보여줍니다.  
  
```cpp  
// user_defined_attributes.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
ref struct Attr : public Attribute {  
   Attr(bool i){}  
   Attr(){}  
};  
  
[Attr]  
ref class MyClass {};  
```  
  
 **예제**  
  
 다음 예는 사용자 지정 특성의 몇 가지 중요한 기능을 보여줍니다.  완벽하게 고객에게 자신을 설명 할 수있는 서버의 인스턴스 : 예를 들어,이 예제는 사용자 지정 특성의 일반적인 사용을 보여줍니다.  
  
```cpp  
// extending_metadata_b.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
  
public enum class Access { Read, Write, Execute };  
  
// Defining the Job attribute:  
[AttributeUsage(AttributeTargets::Class, AllowMultiple=true )]  
public ref class Job : Attribute {  
public:  
   property int Priority {  
      void set( int value ) { m_Priority = value; }  
      int get() { return m_Priority; }  
   }  
  
   // You can overload constructors to specify Job attribute in different ways  
   Job() { m_Access = Access::Read; }  
   Job( Access a ) { m_Access = a; }  
   Access m_Access;  
  
protected:  
   int m_Priority;  
};  
  
interface struct IService {  
   void Run();  
};  
  
   // Using the Job attribute:  
   // Here we specify that QueryService is to be read only with a priority of 2.  
   // To prevent namespace collisions, all custom attributes implicitly   
   // end with "Attribute".   
  
[Job( Access::Read, Priority=2 )]  
ref struct QueryService : public IService {  
   virtual void Run() {}  
};  
  
// Because we said AllowMultiple=true, we can add multiple attributes   
[Job(Access::Read, Priority=1)]  
[Job(Access::Write, Priority=3)]  
ref struct StatsGenerator : public IService {  
   virtual void Run( ) {}  
};  
  
int main() {  
   IService ^ pIS;  
   QueryService ^ pQS = gcnew QueryService;  
   StatsGenerator ^ pSG = gcnew StatsGenerator;  
  
   //  use QueryService  
   pIS = safe_cast<IService ^>( pQS );  
  
   // use StatsGenerator  
   pIS = safe_cast<IService ^>( pSG );  
  
   // Reflection  
   MemberInfo ^ pMI = pIS->GetType();  
   array <Object ^ > ^ pObjs = pMI->GetCustomAttributes(false);  
  
   // We can now quickly and easily view custom attributes for an   
   // Object through Reflection */  
   for( int i = 0; i < pObjs->Length; i++ ) {  
      Console::Write("Service Priority = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->Priority);  
      Console::Write("Service Access = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->m_Access);  
   }  
}  
```  
  
 **Output**  
  
  **서비스 우선 순위 \= 0**  
 **액세스 서비스 \= 쓰기**  
 **서비스 우선 순위 \= 3**  
 **액세스 서비스 \= 쓰기**  
 **서비스 우선 순위 \= 1**  
 **서비스 액세스 \= 읽기** **예제**  
  
 개체 ^ 형식은 variant 데이터 형식을 대체 합니다.  다음은 매개 변수로 ^ 개체의 배열을 사용하는 사용자 지정 특성을 정의합니다.  
  
 인수는 컴파일 타임 상수를 표시하여야합니다. 대부분의 경우 그들은 일정한 리터럴이어야합니다.  
  
 사용자 지정 특성 블록에서 type 값을 반환 하는 방법에 대한 정보는 [typeid](../windows/typeid-cpp-component-extensions.md)를 참조하십시오.  
  
```cpp  
// extending_metadata_e.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class | AttributeTargets::Method)]  
public ref class AnotherAttr : public Attribute {  
public:  
   AnotherAttr(array<Object^>^) {}  
   array<Object^>^ var1;  
};  
  
// applying the attribute  
[ AnotherAttr( gcnew array<Object ^> { 3.14159, "pi" }, var1 = gcnew array<Object ^> { "a", "b" } ) ]  
public ref class SomeClass {};  
```  
  
 **예제**  
  
 런타임은 사용자 지정 특성 클래스의 공용 부분은 직렬화가 가능해야한다는 것을 요구합니다.  사용자 지정 특성을 만들 때 사용자 지정 특성의 명명 된 인수가 컴파일 타임 상수로 제한됩니다.  \(메타 데이터의 클래스 레이아웃에 추가 된 비트의 순서로 생각하시면됩니다.\)  
  
```cpp  
// extending_metadata_f.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct abc {};  
  
[AttributeUsage( AttributeTargets::All )]  
ref struct A : Attribute {  
   A( Type^ ) {}  
   A( String ^ ) {}  
   A( int ) {}  
};  
  
[A( abc::typeid )]  
ref struct B {};  
```  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)