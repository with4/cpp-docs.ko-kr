---
title: "방법: 단순 일치에 정규식 사용(C++/CLI) | Microsoft Docs"
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
  - "IsMatch 메서드"
  - "정규식[C++], 단순 일치"
  - "검색, 부분 문자열 정확히 일치"
  - "문자열[C++], 부분 문자열 정확히 일치"
  - "부분 문자열, 단순 일치"
ms.assetid: 4661f6f3-0f6d-48f2-abe4-cb4770bf9bd5
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 단순 일치에 정규식 사용(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 정규식을 사용하여 정확하게 일치하는 부분 문자열을 찾습니다.  두 개의 문자열을 입력으로 사용하는 정적 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> 메서드를 통해 검색을 수행합니다.  첫 번째 문자열은 검색할 문자열이고, 두 번째 문자열은 검색할 패턴입니다.  
  
## 예제  
  
```  
// regex_simple.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ sentence =   
   {  
      "cow over the moon",  
      "Betsy the Cow",  
      "cowering in the corner",  
      "no match here"  
   };  
  
   String^ matchStr = "cow";  
   for (int i=0; i<sentence->Length; i++)  
   {  
      Console::Write( "{0,24}", sentence[i] );  
      if ( Regex::IsMatch( sentence[i], matchStr,  
                     RegexOptions::IgnoreCase ) )  
         Console::WriteLine("  (match for '{0}' found)", matchStr);  
      else  
         Console::WriteLine("");  
   }  
   return 0;  
}  
```  
  
## 참고 항목  
 [.NET Framework 정규식](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)