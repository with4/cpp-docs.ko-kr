---
title: "방법: 종료 프로세스 시작 여부 확인(C++/CLI) | Microsoft Docs"
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
  - ".NET Framework, 종료"
  - "응용 프로그램[C++], 종료"
  - "종료"
  - "종료"
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 종료 프로세스 시작 여부 확인(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 응용 프로그램이나 .NET Framework가 현재 종료되고 있는지 확인하는 방법을 보여 줍니다.  이러한 구조체는 컴퓨터를 종료하는 동안 시스템에 의해 종료되고 안전하게 사용할 수 없으므로 이 방법은 .NET Framework의 정적 요소에 액세스하는 데 유용합니다.  <xref:System.Environment.HasShutdownStarted%2A> 속성을 먼저 검사하면 이러한 요소에 액세스하지 않아 발생하는 잠재적 문제를 방지할 수 있습니다.  
  
## 예제  
  
```  
// check_shutdown.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   if (Environment::HasShutdownStarted)  
      Console::WriteLine("Shutting down.");  
   else  
      Console::WriteLine("Not shutting down.");  
   return 0;  
}  
```  
  
## 참고 항목  
 [Windows 작업](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)