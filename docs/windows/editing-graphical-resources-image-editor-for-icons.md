---
title: 그래픽 리소스 편집 (아이콘에 대 한 이미지 편집기) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
dev_langs:
- C++
helpviewer_keywords:
- images [C++], editing
- graphics [C++]
- images [C++]
- Image editor [C++], about Image editor
- graphics [C++], Image editor
- graphics [C++], editing
ms.assetid: 09e422c5-f712-4378-b973-c7a3bbc92b9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c6b4aea912398413d43810ad08a2b34e9cb78092
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642388"
---
# <a name="editing-graphical-resources-image-editor-for-icons"></a>그래픽 리소스 편집(아이콘에 대한 이미지 편집기)
그래픽 리소스는 응용 프로그램에 대해 정의 하는 이미지입니다. 자유롭게 그릴 수도 있고 셰이프를 사용 하 여 그릴 수 있습니다. 편집, 대칭 이동 또는 크기 조정에 대 한 이미지의 일부를 선택할 수 있고 이미지의 선택한 부분에서 사용자 지정 브러시 만들기는 브러시를 사용 하 여 그리기 수도 있습니다. 이미지 속성을 정의 하 고, 서로 다른 형식으로 이미지를 저장 하 고, 다른 이미지를 한 형식에서에서 변환 수입니다.  
  
 새 그래픽 리소스를 만들 수 있습니다 [기존 이미지를 가져올](../windows/how-to-import-and-export-resources.md) 편집에 대 한 다음 프로젝트에 추가 하 고 있습니다. 또한을 열고 프로젝트에 포함 되지 않는 이미지도 편집할 [독립 실행형 이미지 편집](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md)합니다.  
  
-   [새 비트맵 또는 다른 이미지 만들기](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)  
  
-   [선택한 그리기 도구 사용](using-a-drawing-tool-image-editor-for-icons.md)  
  
-   [선 또는 닫힌된 그림 그리기](../windows/drawing-lines-or-closed-figures-image-editor-for-icons.md)  
  
-   [이미지 영역 선택](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)  
  
-   [이미지의 선택한 부분을 편집합니다.](../windows/editing-parts-of-an-image-image-editor-for-icons.md)  
  
-   [이미지 대칭 이동](../windows/flipping-an-image-image-editor-for-icons.md)  
  
-   [이미지 크기 조정](../windows/resizing-an-image-image-editor-for-icons.md)  
  
-   [사용자 지정 브러시 만들기](../windows/creating-a-custom-brush-image-editor-for-icons.md)  
  
-   [이미지 속성 변경](changing-image-properties-image-editor-for-icons.md)  
  
-   [비트맵을.gifs 또는.jpegs 저장](../windows/saving-bitmaps-as-gifs-or-jpegs-image-editor-for-icons.md)  
  
-   [이미지를 다른 형식에서 변환합니다.](../windows/converting-an-image-from-one-format-to-another-image-editor-for-icons.md)  
  
-   [프로젝트 외부의 이미지 편집](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md)  
  
-   [이미지 메뉴](../windows/image-menu-image-editor-for-icons.md)  
  
-   [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md)  
  
-   [이미지 편집기 창](../windows/window-panes-image-editor-for-icons.md)  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
> [!NOTE]
>  사용 하 여 **이미지 편집기**, 32 비트 이미지를 볼 수 있지만 편집할 수는 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)   