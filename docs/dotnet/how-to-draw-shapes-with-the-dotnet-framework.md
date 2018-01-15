---
title: "방법:.NET Framework로 도형 그리기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
ms.assetid: ffad5ae7-6ef4-4550-8940-be3f209a101d
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 62579ca21ba4a4dcf89aea6ff717ce6c884073b3
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-draw-shapes-with-the-net-framework"></a>방법: .NET Framework로 도형 그리기
다음 코드 예제에서는 <xref:System.Drawing.Graphics> 수정 하는 클래스는 <xref:System.Windows.Forms.Form.OnPaint%2A> 이벤트 처리기에 대 한 포인터를 검색 하는 <xref:System.Drawing.Graphics> 기본 폼에 대 한 개체입니다. 이 포인터는 다음 폼의 배경색을 설정 하 고 선 및 사용 하 여 호를 그릴 하는 데 사용 됩니다는 <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> 및 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드.  
  
> [!NOTE]
>  GDI + Windows XP에 포함 되어 있으며 Windows NT 4.0 SP 6, Windows 2000, Windows 98 및 Windows me 재배포 가능 구성 요소로 제공 됩니다. 최신 재배포 가능 패키지를 다운로드 하려면 [http://go.microsoft.com/fwlink/p/?linkid=11232](http://go.microsoft.com/fwlink/p/?linkid=11232)합니다. 
  
## <a name="example"></a>예  
  
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
  
## <a name="see-also"></a>참고 항목  
 [.NET 프로그래밍 C + + /cli CLI (Visual c + +)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [System::Drawing 네임 스페이스](https://msdn.microsoft.com/en-us/library/system.drawing.aspx)