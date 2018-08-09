---
title: 아이콘 또는 다른 이미지 (아이콘에 대 한 이미지 편집기) 만들기 | Microsoft Docs
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
- bitmaps [C++]
- images [C++], creating
- resource toolbars
- resources [Visual Studio], creating images
- bitmaps [C++], creating
- graphics [C++], creating
- Image editor [C++], creating images
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b708d701bee433857f8d5f8379d74b92375340de
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651923"
---
# <a name="creating-an-icon-or-other-image-image-editor-for-icons"></a>아이콘 또는 다른 이미지 만들기(아이콘에 대한 이미지 편집기)
새 이미지 (비트맵, 아이콘, 커서 또는 도구 모음)를 만들려면 다음 이미지 편집기를 사용 하 여 모양을 사용자 지정할 수 있습니다. 뒤에 패턴화 새 비트맵을 만들 수도 있습니다는 [템플릿](../windows/how-to-use-resource-templates.md)합니다.  
  
### <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>관리 되지 않는 c + + 프로젝트에 새 이미지 리소스를 추가 하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md),.rc 파일을 마우스 오른쪽 단추로 클릭 한 다음 선택 **삽입 리소스** 바로 가기 메뉴에서. (Cursor와 같은.rc 파일에서 기존 이미지 리소스가 이미 있는 경우 단순히 단추로 클릭 합니다 **커서** 선택한 폴더 **커서 삽입** 바로 가기 메뉴에서.)  
  
    > [!NOTE]
    > 프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  에 [리소스 삽입 대화 상자](../windows/add-resource-dialog-box.md)를 만들려면 원하는 이미지 리소스의 유형을 선택 (**비트맵**예를 들어) 클릭 **새로 만들기**합니다.  
  
     더하기 기호 (**+**)에서 이미지 리소스 형식을 옆에 표시 되는 **삽입 리소스** 대화 상자, 즉 모음 템플릿을 사용할 수 있습니다. 템플릿의 목록을 확장 하는 템플릿을 선택 하 고 클릭 더하기 기호를 클릭 **새로 만들기**합니다.  
  
### <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>.NET 프로그래밍 언어의에서 프로젝트에 새 이미지 리소스를 추가 하려면  
  
1.  **솔루션 탐색기**, 프로젝트 폴더를 마우스 오른쪽 단추로 클릭 (예를 들어 `WindowsApplication1`).  
  
2.  바로 가기 메뉴에서 클릭 **추가**, 선택한 **새 항목 추가**합니다.  
  
3.  에 **범주** 창 확장 합니다 **로컬 프로젝트 항목** 폴더를 선택한 **리소스**합니다.  
  
4.  에 **템플릿** 창 프로젝트에 추가 하려는 리소스 유형을 선택 합니다.  
  
     리소스에서 프로젝트에 추가 됩니다 **솔루션 탐색기** 리소스에서 열어서 합니다 [이미지 편집기](../windows/image-editor-for-icons.md)합니다. 이제 이미지를 수정 하려면 이미지 편집기에서 사용할 수 있는 모든 도구를 사용할 수 있습니다. 관리 되는 프로젝트에 이미지를 추가 하는 방법에 대 한 자세한 내용은 참조 하세요. [디자인 타임에 그림 로드](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms)합니다.  
  
    > [!NOTE]
    >  편집할 관리되는 리소스는 연결된 리소스여야 합니다. Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다. 자세한 내용은 [리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps) 에 *.NET Framework Developer's Guide*합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [아이콘 및 커서: 디스플레이 장치용 이미지 리소스](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [비트맵을 도구 모음으로 변환](../windows/converting-bitmaps-to-toolbars.md)   
 [새 도구 모음 만들기](../windows/creating-new-toolbars.md)   
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [아이콘에 대한 이미지 편집기](../windows/image-editor-for-icons.md)