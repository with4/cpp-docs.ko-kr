---
title: "방법: 정규식을 사용한 찾기 및 바꾸기(C++/CLI) | Microsoft Docs"
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
  - "정규식[C++], 찾기 및 바꾸기"
  - "Replace 메서드"
  - "찾기 및 바꾸기"
ms.assetid: 12fe3e18-fe10-4b25-a221-19dc5eab3821
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 정규식을 사용한 찾기 및 바꾸기(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 정규식 클래스 <xref:System.Text.RegularExpressions.Regex>를 사용하여 찾기 및 바꾸기를 수행하는 방법을 보여 줍니다.  <xref:System.Text.RegularExpressions.Regex.Replace%2A> 메서드를 사용하여 이 작업을 수행합니다.  이 버전은 두 문자열을 입력으로 사용합니다. 첫 번째 문자열은 수정할 문자열이고, 두 번째 문자열은 <xref:System.Text.RegularExpressions.Regex> 개체에 지정한 패턴과 일치하는 부분에 대신 삽입될 문자열입니다.  
  
 이 코드에서는 문자열에 있는 모든 숫자를 밑줄\(\_\)로 바꾼 다음 밑줄을 빈 문자열로 바꿉니다. 결과적으로 모든 숫자가 제거됩니다.  동일한 효과를 한 단계로 얻을 수도 있지만 여기서는 이해를 돕기 위해 두 단계를 사용합니다.  
  
## 예제  
  
```  
// regex_replace.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System::Text::RegularExpressions;  
using namespace System;  
  
int main()  
{  
   String^ before = "The q43uick bro254wn f0ox ju4mped";  
   Console::WriteLine("original  : {0}", before);  
  
   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");  
   String^ after = digitRegex->Replace(before, "_");  
   Console::WriteLine("1st regex : {0}", after);  
  
   Regex^ underbarRegex = gcnew Regex("_");  
   String^ after2 = underbarRegex->Replace(after, "");  
   Console::WriteLine("2nd regex : {0}", after2);  
  
   return 0;  
}  
```  
  
## 참고 항목  
 [.NET Framework 정규식](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)