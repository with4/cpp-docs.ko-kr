---
title: "ADO.NET을 사용하여 데이터 액세스(C++/CLI) | Microsoft Docs"
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
  - ".NET Framework[C++], 데이터 액세스"
  - "ADO.NET[C++]"
  - "데이터[C++], ADO.NET"
  - "데이터 액세스[C++], ADO.NET"
  - "데이터베이스[C++], C++에서 액세스"
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ADO.NET을 사용하여 데이터 액세스(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

데이터 액세스를 위한 .NET Framework API인 ADO.NET에서는 기존 데이터 액세스 솔루션보다 월등하게 강력하고 편리한 기능을 제공합니다.  이 단원에서는 ADO.NET 관련 문제 중 네이티브 형식 마샬링과 같이 Visual C\+\+ 사용자에 고유한 문제에 대해 설명합니다.  
  
 ADO.NET은 CLR\(공용 언어 런타임\)에서 실행됩니다.  따라서 ADO.NET과 상호 작용하는 응용 프로그램도 CLR를 대상으로 해야 합니다.  그러나 이로 인해 네이티브 응용 프로그램에서 ADO.NET을 사용할 수 없는 것은 아닙니다.  다음 예제에서는 네이티브 코드에서 ADO.NET 데이터베이스와 상호 작용하는 방법을 보여 줍니다.  
  
## 단원 내용  
 [방법: ADO.NET용 ANSI 문자열 마샬링](../dotnet/how-to-marshal-ansi-strings-for-adonet-cpp-cli.md)  
  
 [방법: ADO.NET용 BSTR 문자열 마샬링](../dotnet/how-to-marshal-bstr-strings-for-adonet-cpp-cli.md)  
  
 [방법: ADO.NET용 유니코드 문자열 마샬링](../dotnet/how-to-marshal-unicode-strings-for-adonet-cpp-cli.md)  
  
 [방법: ADO.NET용 VARIANT 마샬링](../dotnet/how-to-marshal-a-variant-for-adonet-cpp-cli.md)  
  
 [방법: ADO.NET용 SAFEARRAY 마샬링](../dotnet/how-to-marshal-a-safearray-for-adonet-cpp-cli.md)  
  
## 관련 단원  
  
|단원|설명|  
|--------|--------|  
|[ADO.NET](../Topic/ADO.NET.md)|.NET 프로그래머에게 데이터 액세스 서비스를 노출하는 클래스 집합인 ADO.NET에 대해 간략하게 설명합니다.|  
|[Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/ko-kr/5358a825-e19b-49aa-8214-674ce5fed1da)|Visual C\+\+를 비롯한 .NET 언어를 사용하여 저장 프로시저, 집합체, 트리거, 사용자 정의 함수 및 사용자 정의 형식 등의 데이터베이스 개체를 만들고 Microsoft SQL Server 2005 데이터베이스의 데이터를 검색 및 업데이트하는 방법에 대해 설명합니다.|  
  
## 참고 항목  
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)