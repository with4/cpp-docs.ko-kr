---
title: "방법: 디렉터리의 파일 열거(C++/CLI) | Microsoft Docs"
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
  - "디렉터리[C++], 파일 나열"
  - "파일[C++], 파일 나열"
ms.assetid: ebfc2666-229f-4b94-a9a1-e8f1b5d946d6
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 디렉터리의 파일 열거(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 디렉터리의 파일 목록을 검색하는 방법을 보여 줍니다.  이 예제에서는 하위 디렉터리도 열거합니다.  다음 코드 예제에서는 <xref:System.IO.Directory.GetFiles%2A> <xref:System.IO.Directory.GetFiles%2A> 및 <xref:System.IO.Directory.GetDirectories%2A> 메서드를 사용하여 C:\\Windows 디렉터리의 내용을 표시합니다.  
  
## 예제  
  
```  
// enum_files.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ folder = "C:\\";  
   array<String^>^ dir = Directory::GetDirectories( folder );  
   Console::WriteLine("--== Directories inside '{0}' ==--", folder);  
   for (int i=0; i<dir->Length; i++)  
      Console::WriteLine(dir[i]);  
  
   array<String^>^ file = Directory::GetFiles( folder );  
   Console::WriteLine("--== Files inside '{0}' ==--", folder);  
   for (int i=0; i<file->Length; i++)  
      Console::WriteLine(file[i]);  
  
   return 0;  
}  
```  
  
## 참고 항목  
 [파일 및 스트림 I\/O](../Topic/File%20and%20Stream%20I-O.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)