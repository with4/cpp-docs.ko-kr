---
title: "방법: 텍스트 파일 쓰기(C++/CLI) | Microsoft Docs"
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
  - "파일[C++], 텍스트"
  - "텍스트 파일, C++에서 쓰기"
ms.assetid: 39ecdba6-84e0-485c-a202-84cf6d7b8d4a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 텍스트 파일 쓰기(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 텍스트 파일을 만들고 <xref:System.IO> 네임스페이스에 정의되어 있는 <xref:System.IO.StreamWriter> 클래스를 사용하여 이 파일에 텍스트를 쓰는 방법을 보여 줍니다.  <xref:System.IO.StreamWriter> 생성자에는 만들려는 파일의 이름을 전달합니다.  두 번째 <xref:System.IO.StringWriter> 생성자 인수로 True를 전달하지 않은 경우 해당 파일이 있으면 이 파일을 덮어씁니다.  
  
 그런 다음 <xref:System.IO.StreamWriter.Write%2A> 및 <xref:System.IO.TextWriter.WriteLine%2A> 함수를 사용하여 파일이 작성됩니다.  
  
## 예제  
  
```  
// text_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "textfile.txt";  
  
   StreamWriter^ sw = gcnew StreamWriter(fileName);  
   sw->WriteLine("A text file is born!");  
   sw->Write("You can use WriteLine");  
   sw->WriteLine("...or just Write");  
   sw->WriteLine("and do {0} output too.", "formatted");  
   sw->WriteLine("You can also send non-text objects:");  
   sw->WriteLine(DateTime::Now);  
   sw->Close();  
   Console::WriteLine("a new file ('{0}') has been written", fileName);  
  
   return 0;  
}  
```  
  
## 참고 항목  
 [파일 및 스트림 I\/O](../Topic/File%20and%20Stream%20I-O.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)