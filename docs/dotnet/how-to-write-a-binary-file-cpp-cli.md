---
title: "방법: 이진 파일 쓰기(C++/CLI) | Microsoft Docs"
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
  - "이진 파일, C++에서 쓰기"
  - "파일[C++], 이진"
ms.assetid: 35d97ee6-fc7e-4c36-be18-8bbb3b44b3ae
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 이진 파일 쓰기(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 파일에 이진 데이터를 쓰는 방법을 보여 줍니다.  <xref:System.IO> 네임스페이스의 두 클래스인 <xref:System.IO.FileStream>과 <xref:System.IO.BinaryWriter>가 사용됩니다.  <xref:System.IO.FileStream>은 실제 파일을 나타내고 <xref:System.IO.BinaryWriter>는 이진 액세스를 허용하는 인터페이스를 스트림에 제공합니다.  
  
 다음 코드 예제에서는 정수가 포함된 파일을 이진 형식으로 씁니다.  이 파일은 [방법: 이진 파일 읽기](../dotnet/how-to-read-a-binary-file-cpp-cli.md)에 나와 있는 코드를 사용하여 읽을 수 있습니다.  
  
## 예제  
  
```  
// binary_write.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   array<Int32>^ data = {1, 2, 3, 10000};  
  
   FileStream^ fs = gcnew FileStream("data.bin", FileMode::Create);  
   BinaryWriter^ w = gcnew BinaryWriter(fs);  
  
   try   
   {  
      Console::WriteLine("writing data to file:");  
      for (int i=0; i<data->Length; i++)  
      {  
         Console::WriteLine(data[i]);  
         w->Write(data[i]);  
      }  
   }  
   catch (Exception^)   
   {  
     Console::WriteLine("data could not be written");  
     fs->Close();  
     return -1;  
   }  
  
   fs->Close();  
   return 0;  
}  
```  
  
## 참고 항목  
 [파일 및 스트림 I\/O](../Topic/File%20and%20Stream%20I-O.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)