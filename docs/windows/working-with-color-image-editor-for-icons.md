---
title: (아이콘에 대 한 이미지 편집기) 색 작업 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.color
dev_langs:
- C++
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors, Image editor
- colors [C++]
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1f9016e36ce6b081446a00136445fd7ebdd5a341
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891661"
---
# <a name="working-with-color-image-editor-for-icons"></a>색 작업(아이콘에 대한 이미지 편집기)
이미지 편집기를 처리 하 고 색을 사용자 지정 하는 다양 한 기능을 포함 합니다. 전경 또는 배경 색을 설정 지정, 경계 영역을 색으로 채우기 또는 현재 전경 또는 배경 색으로 사용할 이미지에서 색을 선택 합니다. 도구를 사용할 수는 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md) 색상표에 함께 [색상 창](../windows/colors-window-image-editor-for-icons.md) 이미지를 만드는 합니다.  
  
 흑백 및 컬러 16 이미지에 대 한 모든 색 색상표 색 창에 표시 됩니다. 16 개의 표준 색 외에도 사용자 지정 색을 만들 수 있습니다. 색상표의 색을 변경 이미지에 해당 색 즉시 변경 됩니다.  
  
 경우 256 색 아이콘 및 커서 작업 이미지에 있는 색 속성의 [속성 창](/visualstudio/ide/reference/properties-window) 사용 됩니다. 자세한 내용은 참조 [256 색 아이콘이 나 커서 만들기](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)합니다.  
  
> [!NOTE]
>  이미지 편집기를 사용하여 32비트 이미지를 볼 수는 있지만 편집할 수는 없습니다.  
  
 True-컬러 이미지를 만들 수도 있습니다. 그러나 true 색상 샘플 색상 창;에 있는 전체 색상표에 표시 되지 않습니다. 전경 또는 배경 색 표시기 영역에만 나타납니다. True 색상을 사용 하 여 만드는 [사용자 지정 색 선택 대화 상자](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)합니다. 자세한 내용은 참조 [사용자 지정 또는 색 변경](../windows/customizing-or-changing-colors-image-editor-for-icons.md)합니다.  
  
 디스크에 사용자 지정된 색상표를 저장 하 고 필요에 따라 다시 로드 수 있습니다. 가장 최근에 사용한 색 색상표를 레지스트리에 저장 하 고에 Visual Studio를 시작할 때 자동으로 로드 됩니다.  
  
-   [전경색 또는 배경색 선택](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [색을 사용 하 여 이미지의 경계 영역 채우기](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [다른 곳에 사용 하는 이미지에서 색을 선택](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)  
  
-   [투명 또는 불투명 배경 선택](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [선택 영역에서 색 반전](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [사용자 지정 또는 색 변경](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [색상표 저장 및 서로 다른 로드](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [색상 창](../windows/colors-window-image-editor-for-icons.md)  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   

