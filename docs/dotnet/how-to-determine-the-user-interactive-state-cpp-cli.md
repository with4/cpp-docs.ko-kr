---
title: "방법: 사용자 대화형 상태 확인(C++/CLI) | Microsoft Docs"
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
  - "사용자 대화형 상태"
  - "Visual C++, 사용자 대화형 상태"
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 사용자 대화형 상태 확인(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 코드가 사용자 대화형 컨텍스트에서 실행되고 있는지 확인하는 방법을 보여 줍니다.  <xref:System.Environment.UserInteractive%2A>가 false이면 코드가 서비스 프로세스로 실행되고 있거나 웹 응용 프로그램에서 실행되고 있음을 의미합니다. 이 경우 사용자와 상호 작용하지 말아야 합니다.  
  
## 예제  
  
```  
// user_interactive.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   if ( Environment::UserInteractive )  
      Console::WriteLine("User interactive");  
   else  
      Console::WriteLine("Noninteractive");  
   return 0;  
}  
```  
  
## 참고 항목  
 [Windows 작업](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)