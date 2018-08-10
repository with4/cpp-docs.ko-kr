---
title: (아이콘에 대 한 이미지 편집기) 이미지 크기 조정 | Microsoft Docs
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
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c972f4038da4b4ed1d52fee0b8029b6f48ff3bb
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013875"
---
# <a name="resizing-an-image-image-editor-for-icons"></a>이미지 크기 조정(아이콘에 대한 이미지 편집기)
동작을 **이미지** 이미지 크기 조정 하는 동안 편집기 인지에 따라 달라 집니다 [선택한](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) 전체 이미지 또는의 일부입니다.  
  
 이미지의 일부만 포함 하 여 선택 하는 경우는 **이미지** 편집기 픽셀의 행 이나 열을 삭제 하 고 현재 배경색을 사용 하 여 빈된 영역을 입력 하 여 선택 영역을 축소 하거나 하 여 선택 영역을 늘립니다 그 픽셀의 행 이나 열을 복제 합니다.  
  
 전체 이미지를 포함 하 여 선택 하는 경우는 **이미지** 편집기 중 축소 및 이미지를 자릅니다 및 확장 합니다.  
  
 메커니즘은 두 가지 이미지 크기 조정에 대 한: 크기 조정 핸들 및 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 이미지의 일부나 모두의 크기를 변경 하려면 크기 조정 핸들을 끌 수 있습니다. 끌 수 있는 크기 조정 핸들은 실선입니다. 속이 빈 핸들을 끌 수 없습니다. 사용할 수는 **속성** 창의 전체 크기를 조정할 이미지 선택된 된 부분이 아닌만 합니다.  
  
 ![비트맵의 핸들 크기 조정](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")  
크기 조정 핸들  
  
> [!NOTE]
>  있는 경우는 **바둑판식 모눈** 옵션을 선택 합니다 [모눈 설정 대화 상자](../windows/grid-settings-dialog-box-image-editor-for-icons.md), 다음 바둑판식 모눈에 스냅숏 크기 조정이 합니다. 경우는 **픽셀 모눈** 옵션은 (기본 설정)를 선택 하면 다음 사용 가능한 픽셀 눈금의 크기를 조정 합니다.  
  
-   [전체 이미지 크기 조정](../windows/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [전체 이미지 자르기 또는 확장](cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [전체 이미지 줄이기 또는 늘이기](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [이미지의 일부 또는 늘이기](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)