---
title: "방법: 이진 파일 읽기(C++/CLI) | Microsoft Docs"
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
  - "이진 파일, C++에서 읽기"
  - "파일[C++], 이진"
ms.assetid: 41ad9ad1-5cac-489c-874e-4bb3a649073a
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 이진 파일 읽기(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 <xref:System.IO?displayProperty=fullName>네임 스페이스:<xref:System.IO.FileStream> 및 <xref:System.IO.BinaryReader>의 두 클래스를 사용하여 파일에서 이진 데이터를 읽는 방법을 보여줍니다.  <xref:System.IO.FileStream>은 실제 파일을 나타내고  <xref:System.IO.BinaryReader>는 이진 액세스를 허용하는 인터페이스를 스트림에 제공합니다.  
  
 이 코드 예제에서는 이름이 data.bin이고 이진 형식의 정수를 포함하는 파일을 읽습니다.  이런 종류의 파일에 대한 자세한 내용은 [방법: 이진 파일 쓰기](../dotnet/how-to-write-a-binary-file-cpp-cli.md)를 참조하십시오.  
  
## 예제  
  
```  
// binary_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "data.bin";  
   try  
   {  
      FileStream^ fs = gcnew FileStream(fileName, FileMode::Open);  
      BinaryReader^ br = gcnew BinaryReader(fs);  
  
      Console::WriteLine("contents of {0}:", fileName);  
      while (br->BaseStream->Position < br->BaseStream->Length)  
         Console::WriteLine(br->ReadInt32().ToString());  
  
      fs->Close( );  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("File '{0}' not found", fileName);  
      else  
         Console::WriteLine("Exception: ({0})", e);  
      return -1;  
   }  
   return 0;  
}  
```  
  
## 참고 항목  
 [파일 및 스트림 I\/O](../Topic/File%20and%20Stream%20I-O.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)