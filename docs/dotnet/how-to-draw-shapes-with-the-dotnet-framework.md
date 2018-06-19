---
title: 방법:.NET Framework로 도형 그리기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
ms.assetid: ffad5ae7-6ef4-4550-8940-be3f209a101d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 877e78b1ce4f81af76aa20961ea05d18e64f58f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130037"
---
# <a name="how-to-draw-shapes-with-the-net-framework"></a>방법: .NET Framework로 도형 그리기
다음 코드 예제에서는 <xref:System.Drawing.Graphics> 수정 하는 클래스는 <xref:System.Windows.Forms.Form.OnPaint%2A> 이벤트 처리기에 대 한 포인터를 검색 하는 <xref:System.Drawing.Graphics> 기본 폼에 대 한 개체입니다. 이 포인터는 다음 폼의 배경색을 설정 하 고 선 및 사용 하 여 호를 그릴 하는 데 사용 됩니다는 <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> 및 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드.  
  
## <a name="example"></a>예제  
  
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