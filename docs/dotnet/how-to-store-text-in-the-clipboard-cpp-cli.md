---
title: "방법: 클립보드에 텍스트 저장(C++/CLI) | Microsoft Docs"
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
  - "클립보드, 텍스트 저장"
  - "텍스트, 클립보드에 저장"
ms.assetid: 9996023f-b700-47ad-8ad9-1ba201eaa5a6
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 클립보드에 텍스트 저장(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 <xref:System.Windows.Forms> 네임스페이스에 정의된 <xref:System.Windows.Forms.Clipboard> 개체를 사용하여 문자열을 저장합니다.  이 개체는 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 및 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>라는 두 가지 멤버 함수를 제공합니다.  데이터는 <xref:System.Object>에서 파생된 개체를 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>에 전달하여 클립보드에 저장됩니다.  
  
## 예제  
  
```  
// store_clipboard.cpp  
// compile with: /clr  
#using <System.dll>  
#using <System.Drawing.dll>  
#using <System.Windows.Forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
  
[STAThread] int main()  
{  
   String^ str = "This text is copied into the Clipboard.";  
  
   // Use 'true' as the second argument if  
   // the data is to remain in the clipboard  
   // after the program terminates.  
   Clipboard::SetDataObject(str, true);  
  
   Console::WriteLine("Added text to the Clipboard.");  
  
   return 0;  
}  
```  
  
## 참고 항목  
 [방법: 클립보드에서 텍스트 검색](../dotnet/how-to-retrieve-text-from-the-clipboard-cpp-cli.md)   
 [Windows 작업](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)