---
title: "방법: 리플렉션을 사용하여 어셈블리에 데이터 형식 열거(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "어셈블리[C++]"
  - "어셈블리[C++], 데이터 형식 열거"
  - "데이터 형식[C++], 열거"
  - "public 멤버[C++]"
  - "public 형식[C++]"
  - "리플렉션[C++], 외부 어셈블리"
ms.assetid: c3578e6d-bb99-4599-80e1-ab795305f878
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 리플렉션을 사용하여 어셈블리에 데이터 형식 열거(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드에서는 <xref:System.Reflection>을 사용하여 공용 형식과 멤버를 열거하는 방법을 보여 줍니다.  
  
 아래 코드에서는 로컬 디렉터리나 GAC의 어셈블리 이름을 지정하면 이 어셈블리를 열고 설명을 검색합니다.  검색에 성공하면 각 형식이 공용 멤버와 함께 표시됩니다.  
  
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>에는 파일 확장명을 사용하지 말아야 합니다.  따라서 명령줄 인수로 "mscorlib.dll"을 사용하면 작업에 실패하지만 "mscorlib"만 사용하면 .NET Framework 형식이 결과로 표시됩니다.  어셈블리 이름을 지정하지 않은 경우 이 코드는 현재 어셈블리 내에 있는 형식을 검색하여 보고합니다\(이 코드의 경우 EXE\).  
  
## 예제  
  
```  
// self_reflection.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
using namespace System::Collections;  
  
public ref class ExampleType {  
public:  
   ExampleType() {}  
   void Func() {}  
};  
  
int main() {  
   String^ delimStr = " ";  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ args = Environment::CommandLine->Split( delimiter );  
  
// replace "self_reflection.exe" with an assembly from either the local  
// directory or the GAC  
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");  
   Console::WriteLine(a);  
  
   int count = 0;  
   array<Type^>^ types = a->GetTypes();  
   IEnumerator^ typeIter = types->GetEnumerator();  
  
   while ( typeIter->MoveNext() ) {  
      Type^ t = dynamic_cast<Type^>(typeIter->Current);  
      Console::WriteLine("   {0}", t->ToString());  
  
      array<MemberInfo^>^ members = t->GetMembers();  
      IEnumerator^ memberIter = members->GetEnumerator();  
      while ( memberIter->MoveNext() ) {  
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);  
         Console::Write("      {0}", mi->ToString( ) );  
         if (mi->MemberType == MemberTypes::Constructor)  
            Console::Write("   (constructor)");  
  
         Console::WriteLine();  
      }  
      count++;  
   }  
   Console::WriteLine("{0} types found", count);  
}  
```  
  
## 참고 항목  
 [리플렉션](../dotnet/reflection-cpp-cli.md)