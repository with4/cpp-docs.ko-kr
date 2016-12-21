---
title: "방법: 정규식을 사용하여 데이터 필드 추출(C++/CLI) | Microsoft Docs"
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
  - "데이터[C++], 문자열에서 추출"
  - "형식이 지정된 문자열[C++]"
  - "정규식[C++], 데이터 필드 추출"
  - "문자열[C++], 데이터 추출"
ms.assetid: b581d9b6-630e-48fa-94fe-20b0f7b89b06
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 정규식을 사용하여 데이터 필드 추출(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 서식이 지정된 문자열의 데이터를 정규식을 사용하여 추출하는 방법을 보여 줍니다.  다음 코드 예제에서는 <xref:System.Text.RegularExpressions.Regex> 클래스를 사용하여 전자 메일 주소에 해당하는 패턴을 지정합니다.  이 패턴에는 각 전자 메일 주소의 사용자 및 호스트 이름 부분을 검색하는 데 사용할 수 있는 필드 식별자가 포함됩니다.  <xref:System.Text.RegularExpressions.Match> 클래스는 패턴이 일치하는지 실제로 확인하는 데 사용됩니다.  지정된 전자 메일 주소가 유효하면 사용자 이름과 호스트 이름을 추출하여 표시합니다.  
  
## 예제  
  
```  
// Regex_extract.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
    array<String^>^ address=  
    {  
        "jay@southridgevideo.com",  
        "barry@adatum.com",  
        "treyresearch.net",  
        "karen@proseware.com"  
    };  
  
    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");  
  
    for (int i=0; i<address->Length; i++)  
    {  
        Match^ m = emailregex->Match( address[i] );  
        Console::Write("\n{0,25}", address[i]);  
  
        if ( m->Success )   
        {  
            Console::Write("   User='{0}'",   
            m->Groups["user"]->Value);  
            Console::Write("   Host='{0}'",   
            m->Groups["host"]->Value);  
        }  
        else   
            Console::Write("   (invalid email address)");  
        }  
  
    Console::WriteLine("");  
    return 0;  
}  
```  
  
## 참고 항목  
 [.NET Framework 정규식](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)