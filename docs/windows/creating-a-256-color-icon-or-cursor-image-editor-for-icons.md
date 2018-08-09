---
title: 256 색 아이콘이 나 커서 (아이콘에 대 한 이미지 편집기) 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 256-color palette
- cursors, color
- colors, icons
- colors, cursors
- icons, color
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 92f5a427399009baf1b157480f0e486e9c4ec538
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645225"
---
# <a name="creating-a-256-color-icon-or-cursor-image-editor-for-icons"></a>256색 아이콘 또는 커서 만들기(아이콘에 대한 이미지 편집기)
사용 하 여 **이미지** 편집기, 아이콘 및 커서 선택할 256 색 색상표를 사용 하 여 크기가 큰 (64 × 64) 될 수 있습니다. 리소스를 만든 후 장치 이미지 스타일을 선택 합니다.  
  
### <a name="to-create-a-256-color-icon-or-cursor"></a>256 색 아이콘이 나 커서를 만들려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md),.rc 파일을 마우스 오른쪽 단추로 클릭 한 다음 선택 **삽입 리소스** 바로 가기 메뉴에서. (Cursor와 같은.rc 파일에서 기존 이미지 리소스가 이미 있는 경우 단순히 단추로 클릭 합니다 **커서** 선택한 폴더 **커서 삽입** 바로 가기 메뉴에서.)  
  
    > [!NOTE] 
    > 프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  에 [리소스 삽입 대화 상자](../windows/add-resource-dialog-box.md)를 선택 **아이콘** 또는 **커서** 클릭 **새**합니다.  
  
3.  에 **이미지** 메뉴에서 클릭 **새 장치 이미지**합니다.  
  
4.  원하는 256 색 이미지 스타일을 선택 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [256 색상표 사용](../windows/using-the-256-color-palette-image-editor-for-icons.md)   
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [아이콘 및 커서: 디스플레이 장치용 이미지 리소스](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)