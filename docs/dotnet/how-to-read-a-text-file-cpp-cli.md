---
title: "방법: 텍스트 파일 읽기(C++/CLI) | Microsoft Docs"
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
  - "텍스트 파일 읽기"
  - "텍스트 파일, 읽기"
ms.assetid: 80551c01-d769-4b6d-8db7-fd53bde21b62
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 텍스트 파일 읽기(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 <xref:System.IO?displayProperty=fullName> 네임스페이스에 정의된 <xref:System.IO.StreamReader> 클래스를 사용하여 텍스트 파일을 열고 한 번에 한 줄씩 읽는 방법을 보여 줍니다.  이 클래스의 인스턴스는 텍스트 파일을 여는 데 사용되고 각 줄을 검색하는 데는 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName> 메서드가 사용됩니다.  
  
 이 코드 예제에서는 텍스트가 포함된 textfile.txt라는 파일을 읽습니다.  이런 종류의 파일에 대한 자세한 내용은 [방법: 텍스트 파일 쓰기](../dotnet/how-to-write-a-text-file-cpp-cli.md)를 참조하십시오.  
  
## 예제  
  
```  
// text_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ fileName = "textfile.txt";  
   try   
   {  
      Console::WriteLine("trying to open file {0}...", fileName);  
      StreamReader^ din = File::OpenText(fileName);  
  
      String^ str;  
      int count = 0;  
      while ((str = din->ReadLine()) != nullptr)   
      {  
         count++;  
         Console::WriteLine("line {0}: {1}", count, str );  
      }  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("file '{0}' not found", fileName);  
      else  
         Console::WriteLine("problem reading file '{0}'", fileName);  
   }  
  
   return 0;  
}  
```  
  
## 참고 항목  
 [파일 및 스트림 I\/O](../Topic/File%20and%20Stream%20I-O.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)