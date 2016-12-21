---
title: "방법: 로컬 컴퓨터 이름 검색(C++/CLI) | Microsoft Docs"
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
  - "컴퓨터 이름"
  - "컴퓨터 이름, 검색"
  - "컴퓨터 이름, 검색"
ms.assetid: 6c7acb9a-3f9b-43b2-a756-bd4fb859e697
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 로컬 컴퓨터 이름 검색(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 로컬 컴퓨터 이름\(네트워크에 표시되는 컴퓨터의 이름\)을 검색하는 방법을 보여 줍니다.  이 이름을 검색하려면 <xref:System.Environment> 네임스페이스에 정의되어 있는 <xref:System.Environment.MachineName%2A> 문자열을 가져와야 합니다.  
  
## 예제  
  
```  
// machine_name.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);  
   return 0;  
}  
```  
  
## 참고 항목  
 [Windows 작업](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)