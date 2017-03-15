---
title: "방법: 정규식을 사용하여 문자열 구문 분석(C++/CLI) | Microsoft Docs"
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
  - "예제[C++], 문자열"
  - "문자열 구문 분석[C++]"
  - "정규식[C++], 문자열 구문 분석"
  - "문자열[C++], 구문 분석"
ms.assetid: 5b0c7ca3-9bba-4389-a45c-6d373cff91b0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 정규식을 사용하여 문자열 구문 분석(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 <xref:System.Text.RegularExpressions?displayProperty=fullName> 네임스페이스의 <xref:System.Text.RegularExpressions.Regex> 클래스를 사용하여 간단한 문자열을 구문 분석하는 방법을 보여 줍니다.  여러 형식의 단어 설명자가 포함된 문자열이 생성됩니다.  이 문자열은 <xref:System.Text.RegularExpressions.Match> 클래스와 함께 <xref:System.Text.RegularExpressions.Regex> 클래스를 사용하여 구문 분석됩니다.  그런 다음 문장의 각 단어가 개별적으로 표시됩니다.  
  
## 예제  
  
```  
// regex_parse.cpp  
// compile with: /clr  
#using <system.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main( )  
{  
   int words = 0;  
   String^ pattern = "[a-zA-Z]*";  
   Console::WriteLine( "pattern : '{0}'", pattern );  
   Regex^ regex = gcnew Regex( pattern );  
  
   String^ line = "one\ttwo three:four,five six  seven";     
   Console::WriteLine( "text : '{0}'", line );  
   for( Match^ match = regex->Match( line );   
        match->Success; match = match->NextMatch( ) )   
   {  
      if( match->Value->Length > 0 )  
      {  
         words++;  
         Console::WriteLine( "{0}", match->Value );  
      }  
   }  
   Console::WriteLine( "Number of Words : {0}", words );  
  
   return 0;  
}  
```  
  
## 참고 항목  
 [.NET Framework 정규식](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)