---
title: "방법:.NET Framework로 이미지 파일 형식으로 변환 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: 5d5384b0-b9b7-4262-b9ad-c4cb95f75ee4
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eff94d00f92fe0a52162c986662209168974e072
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-convert-image-file-formats-with-the-net-framework"></a>방법: .NET Framework로 이미지 파일 형식 변환
다음 코드 예제는 <xref:System.Drawing.Image?displayProperty=fullName> 클래스 및 <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> 변환 하 고 이미지 파일을 저장 하는 데 사용 하는 열거형입니다. 다음 코드는.jpg 파일에서 이미지를 로드 하 고.gif 및.bmp 파일 형식으로 저장 합니다.  
  
> [!NOTE]
>  GDI + Windows XP, Windows Server 2003 및 Windows Vista에 포함 되어 있으며 Windows 2000 용 재배포 가능 구성 요소로 제공 됩니다. 최신 재배포 가능 패키지를 다운로드 하려면 [http://go.microsoft.com/fwlink/?linkid=11232](http://go.microsoft.com/fwlink/?linkid=11232)합니다.   
  
## <a name="example"></a>예제  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
using namespace System::Drawing::Imaging;  
  
int main()  
{  
   Image^ image = Image::FromFile("SampleImage.jpg");  
   image->Save("SampleImage.png", ImageFormat::Png);  
   image->Save("SampleImage.bmp", ImageFormat::Bmp);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing>   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)