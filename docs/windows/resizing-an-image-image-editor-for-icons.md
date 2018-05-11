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
ms.openlocfilehash: c6636e1f92907c301c6e66abd63f744375bffeb8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="resizing-an-image-image-editor-for-icons"></a>이미지 크기 조정(아이콘에 대한 이미지 편집기)
이미지 크기를 조정할 때 이미지 편집기 동작은 인지에 따라 [선택한](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) 전체 이미지 또는의 일부입니다.  
  
 이미지의 일부만 포함 하 여 선택 하는 경우 행을 삭제 하 여 선택 영역을 축소 하는 이미지 편집기 또는 열 픽셀의 빈된 영역 이거나 현재 배경색으로 픽셀의 행 이나 열을 복제 하 여 선택 영역을 늘립니다.  
  
 선택 영역 전체 이미지를 포함 하는 경우 이미지 편집기 중 하나를 축소 및 이미지를 또는 잘라냅니다 고 확장 합니다.  
  
 이미지 크기 조정에 대 한 두 가지 메커니즘에 없는: 크기 조정 핸들 및 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 이미지의 일부 또는 모든의 크기를 변경 하려면 크기 조정 핸들을 끌 수 있습니다. 끌 수 있는 크기 조정 핸들은 실선입니다. 비어 있는 핸들은 끌 수 없습니다. 선택된 된 부분이 아닌 전체 이미지만 크기를 조정 하려면 속성 창을 사용할 수 있습니다.  
  
 ![비트맵의 핸들 크기 조정](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")  
크기 조정 핸들  
  
> [!NOTE]
>  타일 모눈 옵션을 선택 해야 하는 경우는 [모눈 설정 대화 상자](../windows/grid-settings-dialog-box-image-editor-for-icons.md)를 다음 크기 조정이 다음 타일 모눈선에 맞춰집니다. 픽셀 모눈 옵션을 선택 (기본 설정) 크기 조정이 사용 가능한 다음 픽셀에 맞춰집니다.  
  
-   [전체 이미지 크기 조정](../windows/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [전체 이미지 자르기 또는 확장](cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [전체 이미지 줄이기 또는 늘이기](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [이미지 일부 줄이기 또는 늘이기](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)

