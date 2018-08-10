---
title: 256 색상표 (아이콘에 대 한 이미지 편집기)를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 256-color palette
- colors, icons and cursors
- cursors, color
- color palettes, 256-color
- palettes, 256-color
- icons, color
ms.assetid: 1506ed00-669b-4a21-b1a4-39b6a84a78bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0287d27d975ce93e88a7a4b70a683188901ca958
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011818"
---
# <a name="using-the-256-color-palette-image-editor-for-icons"></a>256 색상표 사용(아이콘에 대한 이미지 편집기)
그릴을 선택 하 여 256 색상표에서 색을 선택 해야 합니다 **색** 색상표에는 [색 창](../windows/colors-window-image-editor-for-icons.md)합니다.  
  
### <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>큰 아이콘에 대 한 256 색상표에서 색을 선택 하려면  
  
1.  큰 아이콘 또는 커서를 선택 하거나 새 큰 아이콘 또는 커서를 만듭니다.  
  
2.  에 표시 된 256 색에서 색을 선택 합니다 **색** 색상표에는 **색** 창입니다.  
  
     선택한 색은 현재 색으로 표시 됩니다는 **색** 색상표에는 **색** 창입니다.  
  
    > [!NOTE]
    >  256 컬러 이미지에 사용 되는 초기 색상표를 반환한 색상표와 일치 하는 `CreateHalftonePalette` Windows API입니다. Windows shell을 위한 모든 아이콘 색상표 인식 하는 동안 깜박임을 방지 하기 위해이 색상표를 사용 해야 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [256 색 아이콘이 나 커서 만들기](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)   
 [아이콘 및 커서: 디스플레이 장치용 이미지 리소스](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)