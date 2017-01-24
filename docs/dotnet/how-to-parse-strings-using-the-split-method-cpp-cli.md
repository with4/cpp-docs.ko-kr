---
title: "방법: Split 메서드를 사용하여 문자열 구문 분석(C++/CLI) | Microsoft Docs"
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
  - "Split 메서드, 문자열 구문 분석"
  - "문자열[C++], 구문 분석"
ms.assetid: d52d2539-5ebb-4716-86b3-07314dd7e4bd
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: Split 메서드를 사용하여 문자열 구문 분석(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 <xref:System.String.Split%2A?displayProperty=fullName> 메서드를 사용하여 문자열에서 각 단어를 추출하는 방법을 보여 줍니다.  여러 형식의 단어 설명자가 포함된 문자열을 만든 다음 설명자 목록과 함께 <xref:System.String.Split%2A>을 호출하여 이 문자열을 구문 분석합니다.  그런 다음 문장의 각 단어가 개별적으로 표시됩니다.  
  
## 예제  
  
```  
// regex_split.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String^ delimStr = " ,.:\t";  
   Console::WriteLine( "delimiter : '{0}'", delimStr );  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ words;  
   String^ line = "one\ttwo three:four,five six seven";  
  
   Console::WriteLine( "text : '{0}'", line );  
   words = line->Split( delimiter );  
   Console::WriteLine( "Number of Words : {0}", words->Length );  
   for (int word=0; word<words->Length; word++)  
      Console::WriteLine( "{0}", words[word] );  
  
   return 0;  
}  
```  
  
## 참고 항목  
 [.NET Framework 정규식](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)