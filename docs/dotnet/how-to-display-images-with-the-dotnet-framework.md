---
title: 방법:.NET Framework로 이미지 표시 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- GDI+ [C++], displaying images
- graphics [C++], displaying images
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4a7f3ed2d8fe90501b5ef3d0ae5028890fe5290e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128581"
---
# <a name="how-to-display-images-with-the-net-framework"></a>방법: .NET Framework로 이미지 표시
다음 코드 예제에서는 수정 OnPaint 이벤트 처리기에 대 한 포인터를 검색 하는 <xref:System.Drawing.Graphics> 기본 폼에 대 한 개체입니다. <xref:System.Windows.Forms.Form.OnPaint%2A> 함수는 대부분 Visual Studio 응용 프로그램 마법사를 사용 하 여 만든 Windows Forms 응용 프로그램을 위한 것입니다.  
  
 이미지가 표시 됩니다는 <xref:System.Drawing.Image> 클래스입니다. 이미지 데이터가 사용 하 여.jpg 파일에서 로드 되는 <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> 메서드. 이미지를 폼에 그릴 전에 폼 이미지에 맞게 크기가 조정 됩니다. 이미지를 그리는 하 여 수행 됩니다는 <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> 메서드.  
  
 <xref:System.Drawing.Graphics> 및 <xref:System.Drawing.Image> 클래스는 모두는 <xref:System.Drawing?displayProperty=fullName> 네임 스페이스입니다.  
  
## <a name="example"></a>예제  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing?displayProperty=fullName>   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)