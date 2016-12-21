---
title: "방법: 정규식을 사용하여 데이터 형식 유효성 검사(C++/CLI) | Microsoft Docs"
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
  - "데이터[C++], 서식 지정"
  - "정규식[C++], 데이터 형식 유효성 검사"
  - "문자열[C++], 서식 지정"
ms.assetid: 225775c3-3efc-4734-bde2-1fdf73e3d397
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 정규식을 사용하여 데이터 형식 유효성 검사(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 정규식을 사용하여 문자열 서식을 검사하는 방법을 보여 줍니다.  이 예제에서는 문자열에 올바른 전화 번호가 포함되어야 합니다.  다음 코드에서는 각 필드가 올바른 전화 번호를 나타내도록 지정하기 위해 "\\d{3}\-\\d{3}\-\\d{4}" 문자열을 사용합니다.  문자열에 있는 "d"는 숫자를 나타내고 각 "d"의 뒤에 있는 인수는 숫자의 개수를 나타냅니다.  이 경우 숫자는 대시 문자\(\-\)로 구분되어야 합니다.  
  
## 예제  
  
```  
// regex_validate.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ number =   
   {  
      "123-456-7890",   
      "444-234-22450",   
      "690-203-6578",   
      "146-893-232",  
      "146-839-2322",  
      "4007-295-1111",   
      "407-295-1111",   
      "407-2-5555",   
   };  
  
   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";  
  
   for ( int i = 0; i < number->Length; i++ )  
   {  
      Console::Write( "{0,14}", number[i] );  
  
      if ( Regex::IsMatch( number[i], regStr ) )  
         Console::WriteLine(" - valid");  
      else  
         Console::WriteLine(" - invalid");  
   }  
   return 0;  
}  
```  
  
## 참고 항목  
 [.NET Framework 정규식](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)