---
title: "방법: 파일 정보 검색(C++/CLI) | Microsoft Docs"
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
  - "FileInfo 클래스"
  - "파일[C++], 정보 검색"
ms.assetid: 8b67f7ad-a048-4437-ac5c-b41809a6018d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 파일 정보 검색(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 <xref:System.IO.FileInfo> 클래스를 보여 줍니다.  파일의 이름을 알고 있으면 이 클래스를 사용하여 파일 크기, 디렉터리, 전체 이름, 파일을 만들거나 마지막으로 수정한 날짜 및 시간 같은 파일 관련 정보를 검색할 수 있습니다.  
  
 이 코드에서는 Notepad.exe에 대한 파일 정보를 검색합니다.  
  
## 예제  
  
```  
// file_info.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   array<String^>^ args = Environment::GetCommandLineArgs();  
   if (args->Length < 2)  
   {  
      Console::WriteLine("\nUSAGE : file_info <filename>\n\n");  
      return -1;  
   }  
  
   FileInfo^ fi = gcnew FileInfo( args[1] );  
  
   Console::WriteLine("file size: {0}", fi->Length );  
  
   Console::Write("File creation date:  ");  
   Console::Write(fi->CreationTime.Month.ToString());  
   Console::Write(".{0}", fi->CreationTime.Day.ToString());  
   Console::WriteLine(".{0}", fi->CreationTime.Year.ToString());  
  
   Console::Write("Last access date:  ");  
   Console::Write(fi->LastAccessTime.Month.ToString());  
   Console::Write(".{0}", fi->LastAccessTime.Day.ToString());  
   Console::WriteLine(".{0}", fi->LastAccessTime.Year.ToString());  
  
   return 0;  
}  
```  
  
## 참고 항목  
 [파일 및 스트림 I\/O](../Topic/File%20and%20Stream%20I-O.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)