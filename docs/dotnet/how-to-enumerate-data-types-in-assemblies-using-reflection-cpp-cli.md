---
title: "방법: 리플렉션을 사용 하 여 데이터 형식 열거 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: c3578e6d-bb99-4599-80e1-ab795305f878
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 209124e6d4e8afa7930a4c74d2cce1acd7e279b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-enumerate-data-types-in-assemblies-using-reflection-ccli"></a>방법: 리플렉션을 사용하여 어셈블리에 데이터 형식 열거(C++/CLI)
다음 코드에서는 공용 형식 및 멤버를 사용 하 여 열거 <xref:System.Reflection>합니다.  
  
 아래 코드 지정 된 어셈블리의 이름을 로컬 디렉터리 또는 GAC에 어셈블리를 열고 설명 검색을 시도 합니다. 성공 하면 public 멤버와 각 형식이 표시 됩니다.  
  
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 없는 파일 확장명으로 사용 됩니다. 따라서 "mscorlib.dll" 명령줄 인수로 사용 하 여 실패 합니다 "mscorlib"를 사용 하 여.NET Framework 형식 표시 발생 됩니다. 제공 된 어셈블리 이름이 없는 경우 코드에서는 검색 하 고 보고서는 현재 어셈블리 내의 형식을 (이 코드에서 발생 하는 EXE).  
  
## <a name="example"></a>예  
  
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
  
## <a name="see-also"></a>참고 항목  
 [리플렉션(C++/CLI)](../dotnet/reflection-cpp-cli.md)