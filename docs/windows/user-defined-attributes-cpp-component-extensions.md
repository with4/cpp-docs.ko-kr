---
title: "사용자 지정 특성 (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- metadata, extending
- custom attributes, extending metadata
ms.assetid: 98b29048-a3ea-4698-8441-f149cdaec9fb
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d974e8526f983801ed011520f7f78ff8c6cb564
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="user-defined-attributes--c-component-extensions"></a>사용자 정의 특성(C++ 구성 요소 확장)
사용자 지정 특성을 사용 하는 인터페이스, 클래스 또는 구조, 메서드, 매개 변수 또는 열거형의 메타 데이터를 확장할 수 있습니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 모든 런타임 사용자 지정 특성을 지원 합니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 C + + /cli CX attributes만 속성을 지원 하지만 하지 생성자 또는 메서드 특성입니다.  
  
### <a name="remarks"></a>설명  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
 사용자 지정 특성을 통해 관리 되는 요소의 메타 데이터를 확장할 수 있습니다. 자세한 내용은 [특성](/dotnet/standard/attributes/index)을 참조하세요.  
  
### <a name="remarks"></a>설명  
 정보 및이 항목에 제시 된 구문은에 제시 된 정보를 대체 하기 위한 것 [특성](../windows/attribute.md)합니다.  
  
 형식을 정의 하 여 사용자 지정 특성을 정의할 수 있습니다 <xref:System.Attribute> 기본 클래스 형식에 대 한 이동 하 고 선택적으로 적용는 <xref:System.AttributeUsageAttribute> 특성입니다.  
  
 예를 들어에 Microsoft Transaction Server (MTS) 1.0, 트랜잭션, 동기화, 관련 하 여 동작 부하 분산, 및 등 ODL 사용자 지정 특성을 사용 하 여 형식 라이브러리에 삽입 하는 사용자 지정 Guid를 통해 지정 된 합니다. 따라서 MTS 서버의 클라이언트 형식 라이브러리를 참조 하 여 해당 특성을 지정할 수 없습니다. .NET Framework에서 형식 라이브러리의 메타 데이터를 이며 ODL 사용자 지정 특성의 사용자 지정 특성입니다. 또한 형식 라이브러리를 읽기는 리플렉션을 사용 하 여 형식에과 같습니다.  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
-   [특성 대상](../windows/attribute-targets-cpp-component-extensions.md)  
  
-   [특성 매개 변수 형식](../windows/attribute-parameter-types-cpp-component-extensions.md)  
  
 Visual c + +에서 어셈블리 서명에 대 한 자세한 내용은 참조 하십시오. [강력한 이름 어셈블리 (어셈블리 서명) (C + + /cli CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 샘플에는 사용자 지정 특성을 정의 하는 방법을 보여 줍니다.  
  
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
  
 다음 예제에서는 사용자 지정 특성의 몇 가지 중요 한 기능을 보여 줍니다. 예를 들어 사용자 지정 특성의 일반적인 사용을 보여 주는이 예제: 인스턴스화 완벽 하 게 클라이언트에 자체 설명할 수 있는 서버.  
  
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
  
 **출력**  
  
```Output  
Service Priority = 0  
  
Service Access = Write  
  
Service Priority = 3  
  
Service Access = Write  
  
Service Priority = 1  
  
Service Access = Read  
```  
  
 **예제**  
  
 개체 ^ 형식이 variant 데이터 형식을 대체 합니다. 다음 예제에서는 개체의 배열을 사용 하는 사용자 지정 특성을 정의 ^ 매개 변수로 합니다.  
  
 특성 인수가 컴파일 시간 상수; 이어야 합니다. 대부분의 경우에서 상수 리터럴 수 있어야 합니다.  
  
 참조 [typeid](../windows/typeid-cpp-component-extensions.md) system:: type 값은 사용자 지정 특성 블록에서 반환 하는 방법에 대 한 내용은 합니다.  
  
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
  
 런타임에는 사용자 지정 특성 클래스의 공용 부분 직렬화 해야 필요 합니다.  사용자 지정 특성을 만들 때 사용자 지정 특성의 명명 된 인수는 컴파일 시간 상수 제한 됩니다.  (것으로 생각 하면 일련의 메타 데이터에 클래스 레이아웃에 추가 하는 비트.)  
  
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
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)