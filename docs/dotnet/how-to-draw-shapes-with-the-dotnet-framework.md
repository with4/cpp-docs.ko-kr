---
title: "방법: .NET Framework로 도형 그리기 | Microsoft Docs"
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
  - "그리기, 도형"
  - "GDI+, 도형 그리기"
  - "도형"
  - "도형, 그리기"
ms.assetid: ffad5ae7-6ef4-4550-8940-be3f209a101d
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: .NET Framework로 도형 그리기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 <xref:System.Drawing.Graphics> 클래스를 사용하여 <xref:System.Windows.Forms.Form.OnPaint%2A> 이벤트 처리기를 수정하고 기본 폼의 <xref:System.Drawing.Graphics> 개체에 대한 포인터를 검색합니다.  그런 다음 이 포인터를 사용하여 폼의 배경색을 설정하고 <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> 및 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드를 사용하여 직선과 원호를 그립니다.  
  
> [!NOTE]
>  GDI\+는 Windows XP에 포함되어 있으며 Windows NT 4.0 SP 6, Windows 2000, Windows 98 및 Windows Me를 위한 재배포 가능 파일로도 구할 수 있습니다.  To download the latest redistributable, see [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232).  자세한 내용은 [GDI\+](_gdiplus_GDI_start_cpp)를 참조하십시오.  
  
## 예제  
  
```  
#using <system.drawing.dll>  
using namespace System;  
using namespace System::Drawing;  
// ...  
protected:   
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override  
{  
   Graphics^ g = pe->Graphics;  
   g->Clear(Color::AntiqueWhite);  
  
   Rectangle rect = Form::ClientRectangle;  
   Rectangle smallRect;  
   smallRect.X = rect.X + rect.Width / 4;  
   smallRect.Y = rect.Y + rect.Height / 4;  
   smallRect.Width = rect.Width / 2;  
   smallRect.Height = rect.Height / 2;  
  
   Pen^ redPen = gcnew Pen(Color::Red);  
   redPen->Width = 4;  
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);  
  
   Pen^ bluePen = gcnew Pen(Color::Blue);  
   bluePen->Width = 10;  
   g->DrawArc( bluePen, smallRect, 90, 270 );  
}  
```  
  
## 참고 항목  
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [System::Drawing 네임스페이스](https://msdn.microsoft.com/en-us/library/system.drawing.aspx)