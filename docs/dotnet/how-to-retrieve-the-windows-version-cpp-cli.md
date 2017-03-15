---
title: "방법: Windows 버전 검색(C++/CLI) | Microsoft Docs"
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
  - "Windows[C++], Visual C++를 사용하여 버전 검색"
  - "Windows[C++], 버전"
ms.assetid: 7e6f567b-d378-49bb-aa59-2240f69a022d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: Windows 버전 검색(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 현재 운영 체제의 플랫폼 및 버전 정보를 검색하는 방법을 보여 줍니다.  이 정보는 <xref:System.Environment.OSVersion%2A?displayProperty=fullName> 속성에 저장되어 있고, 넓은 의미에서의 Windows 버전을 설명하는 열거형과 운영 체제의 정확한 빌드가 포함된 <xref:System.Environment.Version%2A> 개체로 구성되어 있습니다.  
  
## 예제  
  
```  
// os_ver.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   OperatingSystem^ osv = Environment::OSVersion;  
   PlatformID id = osv->Platform;  
   Console::Write("Operating system: ");  
  
   if (id == PlatformID::Win32NT)  
      Console::WriteLine("Win32NT");  
   else if (id == PlatformID::Win32S)  
      Console::WriteLine("Win32S");  
   else if (id == PlatformID::Win32Windows)  
      Console::WriteLine("Win32Windows");  
   else  
      Console::WriteLine("WinCE");  
  
   Version^ version = osv->Version;  
   if (version)  
   {  
      int build = version->Build;  
      int major = version->Major;  
      int minor = version->Minor;  
      int revision = Environment::Version->Revision;  
      Console::Write("OS Version: ");  
      Console::WriteLine("{0}.{1}.{2}.{3}",   
                   build, major, minor, revision);  
   }  
  
   return 0;  
}  
```  
  
## 참고 항목  
 [Windows 작업](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)