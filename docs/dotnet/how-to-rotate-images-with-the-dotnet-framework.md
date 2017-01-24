---
title: "방법: .NET Framework로 이미지 회전 | Microsoft Docs"
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
  - "GDI+[C++], 이미지 회전"
  - "그래픽[C++], 이미지 회전"
ms.assetid: e32104d5-87d0-47a9-a22f-9bc835b7e8d7
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: .NET Framework로 이미지 회전
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 <xref:System.Drawing.Image?displayProperty=fullName> 클래스를 사용하여 디스크에서 이미지를 로드하고, 이 이미지를 90도 회전시킨 다음 새 .jpg 파일로 저장하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  GDI\+는 Windows XP에 포함되어 있으며 Windows NT 4.0 SP 6, Windows 2000, Windows 98 및 Windows Millennium Edition을 위한 재배포 가능 파일로도 구할 수 있습니다.  To download the latest redistributable, see [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232).  자세한 내용은 [GDI\+](_gdiplus_GDI_start_cpp)를 참조하십시오.  
  
## 예제  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
  
int main()  
{  
   Image^ image = Image::FromFile("SampleImage.jpg");  
   image->RotateFlip( RotateFlipType::Rotate90FlipNone );  
   image->Save("SampleImage_rotated.jpg");  
   return 0;  
}  
```  
  
## 참고 항목  
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)