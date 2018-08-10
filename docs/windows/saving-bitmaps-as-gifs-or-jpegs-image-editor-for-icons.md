---
title: 비트맵을 Gif 또는 Jpeg (아이콘에 대 한 이미지 편집기) 저장 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.editing
dev_langs:
- C++
helpviewer_keywords:
- .gif files, saving bitmaps as
- jpg files, saving bitmaps as
- jpeg files, saving bitmaps as
- .jpg files, saving bitmaps as
- Image editor [C++], converting image formats
- gif files, saving bitmaps as
- bitmaps [C++], converting formats
- .jpeg files, saving bitmaps as
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 115df69f-10fb-4e6f-906b-853c1e4a54af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: debb2b1e8435cc53ec82ab1f957710850d7b5de3
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010693"
---
# <a name="saving-bitmaps-as-gifs-or-jpegs-image-editor-for-icons"></a>비트맵을 GIF 또는 JPEG로 저장(아이콘에 대한 이미지 편집기)
비트맵을 만들 때 이미지 비트맵 (.bmp) 형식으로 만들어집니다. 그러나 GIF 또는 JPEG로 또는 다른 그래픽 형식의 이미지를 저장할 수 있습니다.  
  
> [!NOTE]
>  이 프로세스는 아이콘과 커서에는 적용 되지 않습니다.  
  
### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>만들고.jpeg 또는.gif 비트맵을 저장 하려면  
  
1.  **파일** 메뉴 선택 **열려**, 클릭 **파일**합니다.  
  
2.  에 **새 파일 대화 상자**, 클릭는 **Visual c + +** 폴더를 선택한 **비트맵 파일 (.bmp)** 에 **템플릿** 상자 하 고 클릭  **열기**합니다.  
  
     에 비트맵이 열립니다는 **이미지** 편집기입니다.  
  
3.  필요에 따라 새 비트맵을 변경 합니다.  
  
4.  열려 있는 상태에서 비트맵을 사용 하 여 합니다 **이미지** 편집기를 클릭 합니다 **저장 *filename*으로.bmp** 에 **파일** 메뉴.  
  
5.  에 **다른 이름으로 파일 저장** 대화 상자 파일과에서 원하는 파일 형식에 맞게 확장에 지정할 이름을 입력 합니다 합니다 **파일 이름** 상자. 예를 들어 *myfile.gif*합니다.  
  
     > [!NOTE]
     > 만들거나 해야 다른 파일 형식으로 저장 하기 위해 프로젝트 외부에서 비트맵을 엽니다. 만들거나 프로젝트 내에서 열을 **다른 이름으로 저장** 명령을 사용할 수 없게 됩니다. 자세한 내용은 [보기 리소스 (독립 실행형) 프로젝트 외부에서 리소스 스크립트 파일 열기](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)합니다.  
  
6.  **저장**을 클릭합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)