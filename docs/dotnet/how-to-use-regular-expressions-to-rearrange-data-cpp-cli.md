---
title: "방법: 정규식을 사용하여 데이터 다시 정렬(C++/CLI) | Microsoft Docs"
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
  - "데이터[C++], 다시 정렬"
  - "정규식[C++], 데이터 다시 정렬"
ms.assetid: 5f91e777-9471-424e-ba75-dca3d1b49e42
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 정규식을 사용하여 데이터 다시 정렬(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 .NET Framework 정규식 지원을 사용하여 데이터를 다시 정렬하거나 형식을 바꾸는 방법을 보여 줍니다.  다음 코드 예제에서는 <xref:System.Text.RegularExpressions.Regex> 및 <xref:System.Text.RegularExpressions.Match> 클래스를 사용하여 문자열에서 이름과 성을 추출한 다음 이러한 이름 요소의 순서를 바꿔 표시합니다.  
  
 <xref:System.Text.RegularExpressions.Regex> 클래스는 데이터의 현재 형식을 설명하는 정규식을 생성하는 데 사용됩니다.  두 이름은 쉼표로 구분되는 것으로 가정하고 쉼표 앞뒤에 공백을 그 수에 상관없이 추가할 수 있는 것으로 가정합니다.  <xref:System.Text.RegularExpressions.Match> 메서드는 각 문자열을 분석하는 데 사용됩니다.  문자열이 분석되면 <xref:System.Text.RegularExpressions.Match> 개체에서 이름과 성을 검색하여 표시합니다.  
  
## 예제  
  
```  
// regex_reorder.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ name =   
   {  
      "Abolrous, Sam",   
      "Berg,Matt",   
      "Berry , Jo",  
      "www.contoso.com"  
   };  
  
   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");  
  
   for ( int i=0; i < name->Length; i++ )  
   {  
      Console::Write( "{0,-20}", name[i] );  
      Match^ m = reg->Match( name[i] );  
      if ( m->Success )  
      {  
         String^ first = m->Groups["first"]->Value;  
         String^ last = m->Groups["last"]->Value;  
         Console::WriteLine("{0} {1}", first, last);  
      }  
      else  
         Console::WriteLine("(invalid)");  
   }  
   return 0;  
}  
```  
  
## 참고 항목  
 [.NET Framework 정규식](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)