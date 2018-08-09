---
title: 색 (아이콘에 대 한 이미지 편집기)를 사용 하 여 작업 | Microsoft Docs
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
ms.openlocfilehash: 37e469b18af727bea29681b284fd123bcce64c93
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647422"
---
# <a name="working-with-color-image-editor-for-icons"></a>색 작업(아이콘에 대한 이미지 편집기)
합니다 **이미지 편집기** 처리 하 고 색을 사용자 지정 하는 많은 기능이 포함 되어 있습니다. 전경 또는 배경 색을 설정 하, 색을 사용 하 여 제한 된 영역을 입력 하거나 현재 전경 또는 배경 색으로 사용할 이미지의 색을 선택할 수 있습니다. 도구를 사용할 수는 [이미지 편집기 도구 모음](../windows/toolbar-image-editor-for-icons.md) 색상표에 함께 합니다 [색 창](../windows/colors-window-image-editor-for-icons.md) 이미지를 만들 수.  
  
 흑백 및 컬러 16 이미지에 대 한 모든 색에 표시 됩니다는 **색** 색상표에는 **색** 창입니다. 16 개의 표준 색이 외에도 사용자 지정 색을 만들 수 있습니다. 즉시 색상표의 색을 변경 그림과에서 해당 색을 변경 합니다.  
  
 256 색 아이콘 및 커서 이미지를 사용 하 여 작업 하는 경우는 **색** 속성에는 [속성 창](/visualstudio/ide/reference/properties-window) 사용 됩니다. 자세한 내용은 [256 색 아이콘이 나 커서 만들기](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)합니다.  
  
> [!NOTE]
>  사용 하 여 **이미지 편집기**, 32 비트 이미지를 볼 수 있지만 편집할 수는 없습니다.  
  
 True-컬러 이미지를 만들 수도 있습니다. 그러나 true 색상 샘플 나타나지 전체 색상표에는 **색** 창 전경 또는 배경 색 표시기 영역에만 나타납니다. True 색을 사용 하 여 만들어집니다 합니다 [사용자 지정 색 선택 대화 상자](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)합니다. 자세한 내용은 [사용자 지정 색을 변경 하거나](../windows/customizing-or-changing-colors-image-editor-for-icons.md)합니다.  
  
 사용자 지정된 색상표를 디스크에 저장 하 고 필요에 따라 다시 로드 수 있습니다. 가장 최근에 사용한 색 색상표를 레지스트리에 저장 하 고에 Visual Studio를 시작할 때 자동으로 로드 합니다.  
  
-   [전경색 또는 배경색 선택](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [색을 사용 하 여 이미지의 경계 영역 채우기](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [다른 곳에 사용 하는 이미지에서 색을 선택](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)  
  
-   [투명 또는 불투명 배경 선택](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [선택 영역에서 색 반전](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [사용자 지정 또는 색 변경](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [색상표 저장 및 다른 로드](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [색상 창](../windows/colors-window-image-editor-for-icons.md)  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   