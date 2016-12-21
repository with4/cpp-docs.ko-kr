---
title: "방법: .NET Framework로 이미지 표시 | Microsoft Docs"
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
  - "GDI+[C++], 이미지 표시"
  - "그래픽[C++], 이미지 표시"
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: .NET Framework로 이미지 표시
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 OnPaint 이벤트 처리기를 수정하여 기본 폼의 <xref:System.Drawing.Graphics> 개체에 대한 포인터를 검색합니다.  <xref:System.Windows.Forms.Form.OnPaint%2A> 함수는 대개 Visual Studio 응용 프로그램 마법사로 작성되는 Windows Forms 응용 프로그램에 사용하기 위한 것입니다.  
  
 이미지는 <xref:System.Drawing.Image> 클래스로 표현됩니다.  이미지 데이터는 <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> 메서드를 사용하여 .jpg 파일에서 로드됩니다.  폼에 이미지를 그리기 전에 이미지에 맞도록 폼의 크기가 조정됩니다.  이미지를 그리는 데는 <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> 메서드가 사용됩니다.  
  
 <xref:System.Drawing.Graphics> 및 <xref:System.Drawing.Image> 클래스는 모두 <xref:System.Drawing?displayProperty=fullName> 네임스페이스에 있습니다.  
  
> [!NOTE]
>  GDI\+는 Windows XP에 포함되어 있으며 Windows NT 4.0 SP 6, Windows 2000, Windows 98 및 Windows Me를 위한 재배포 가능 파일로도 구할 수 있습니다.  To download the latest redistributable, see [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232).  자세한 내용은 [GDI\+](_gdiplus_GDI_start_cpp)에서 GDI\+ SDK 설명서를 참조하십시오.  
  
## 예제  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
  
protected:  
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override  
{  
    Graphics^ g = pe->Graphics;  
    Image^ image = Image::FromFile("SampleImage.jpg");  
    Form::ClientSize = image->Size;  
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );  
}  
```  
  
## 참고 항목  
 <xref:System.Drawing?displayProperty=fullName>   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)