---
title: 비트맵을 도구 모음으로 변환 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bitmaps [C++], converting to toolbars
- Toolbar editor, converting bitmaps
- toolbars [C++], converting bitmaps
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 74829769644c28cf13a6a6a2631f9bbef1e602a9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645521"
---
# <a name="converting-bitmaps-to-toolbars"></a>비트맵을 도구 모음으로 변환
비트맵을 변환 하 여 새 도구 모음을 만들 수 있습니다. 비트맵에서 그래픽 도구 모음 단추 이미지를 변환합니다. 일반적으로 비트맵 각 단추에 대 한 하나의 이미지를 사용 하 여 단일 비트맵에 여러 단추 이미지를 포함합니다. 모든 크기를 수 있는 이미지 기본값인 16 픽셀 너비 및 이미지의 높이입니다. 단추 이미지의 크기를 지정할 수 있습니다 합니다 [새 도구 모음 리소스 대화 상자](../windows/new-toolbar-resource-dialog-box.md) 선택 하면 **도구 모음 편집기** 에서 합니다 **이미지** 이미지 편집기의 메뉴.  
  
### <a name="to-convert-bitmaps-to-a-toolbar"></a>비트맵을 도구 모음을 변환 하려면  
  
1.  기존 비트맵 리소스를 엽니다는 [이미지 편집기](../windows/image-editor-for-icons.md)합니다. (.Rc 파일을 마우스 오른쪽 단추로 클릭 비트맵에에서 없는 경우 이미.rc 파일을 선택 합니다 **가져오기** 바로 가기 메뉴에서.rc 파일을 추가 하려는 비트맵을 이동한 다음 클릭 **오픈**.)  
  
2.  **이미지** 메뉴 선택 **도구 모음 편집기**합니다.  
  
     합니다 [새 도구 모음 리소스 대화 상자](../windows/new-toolbar-resource-dialog-box.md) 나타납니다. 비트맵에 맞게 아이콘 이미지의 높이 너비를 변경할 수 있습니다. 도구 모음 편집기에서 도구 모음 이미지가 표시 됩니다.  
  
3.  변환이 완료 명령을 변경 **ID** 사용 하 여 단추를 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 새 입력 **ID** 누르거나는 **ID** 드롭 다운 목록에서.  
  
    > [!TIP]
    >  합니다 **속성** 창 제목 표시줄에 압정 단추를 포함 합니다. 이 단추를 클릭 하면 사용 하거나 사용 하지 않도록 설정 **자동 숨기기** 창에 대 한 합니다. 각 속성 창을 다시 열 필요가 없는 모든 도구 모음 단추 속성을 통해 신속 하 게 전환, 전환 **자동 숨기기** 해제 하므로 **속성** 창이 고정 합니다.  
  
 사용 하 여 새 도구 모음에서 단추 명령 Id를 변경할 수도 있습니다는 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 새 도구 모음 편집에 대 한 자세한 내용은 [만들기, 이동 및 편집 도구 모음 단추](../windows/creating-moving-and-editing-toolbar-buttons.md)합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 MFC 또는 ATL  
  
## <a name="see-also"></a>참고 항목  
 [새 도구 모음 만들기](../windows/creating-new-toolbars.md)   
 [도구 모음 편집기](../windows/toolbar-editor.md)