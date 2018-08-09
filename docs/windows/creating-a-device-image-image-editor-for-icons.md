---
title: 장치 이미지 (아이콘에 대 한 이미지 편집기) 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], creating
- icons [C++], creating
- display devices
- display devices, creating image
- images [C++], creating for display devices
- icons [C++], inserting
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bbdc52cca73d568cb365deb345ec6465488e3b40
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641345"
---
# <a name="creating-a-device-image-image-editor-for-icons"></a>장치 이미지 만들기(아이콘에 대한 이미지 편집기)
새 아이콘 또는 커서 리소스를 만들 때 합니다 **이미지** 편집기 (32 × 32 아이콘에 대 한 16 색 32 × 32, 커서에 대 한 단색) 특정 스타일에서 이미지를 먼저 만듭니다. 그런 다음 초기 아이콘이 나 커서에 다양 한 크기 및 스타일 이미지를 추가 하 고 디스플레이 장치에 대 한 필요에 따라 각 추가 이미지를 편집할 수 있습니다. 또한 기존 이미지 형식에서 또는 그래픽 프로그램에서 만든 비트맵에서 잘라내기 / 붙여넣기 작업을 수행 하 여 이미지를 편집할 수 있습니다.  
  
 아이콘 또는 커서 리소스를 열면 합니다 [이미지 편집기](../windows/image-editor-for-icons.md), 기본적으로 열려 대부분의 현재 디스플레이 장치에 밀접 하 게 일치 하는 이미지입니다.  
  
### <a name="to-create-a-new-icon-or-cursor"></a>새 아이콘 또는 커서를 만들려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md),.rc 파일을 마우스 오른쪽 단추로 클릭 한 다음 선택 **삽입 리소스** 바로 가기 메뉴에서. (Cursor와 같은.rc 파일에서 기존 이미지 리소스가 이미 있는 경우 단순히 단추로 클릭 합니다 **커서** 선택한 폴더 **커서 삽입** 바로 가기 메뉴에서.)  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  에 [리소스 삽입 대화 상자](../windows/add-resource-dialog-box.md)를 선택 **아이콘** 또는 **커서** 클릭 **새**합니다. 아이콘에 대 한 32 × 32를 16 색 아이콘으로 아이콘 리소스를 만듭니다. 커서의 경우 32 × 32 단색 (2-색) 이미지가 생성 됩니다.  
  
     더하기 기호 (**+**)에서 이미지 리소스 형식을 옆에 표시 되는 **삽입 리소스** 대화 상자, 즉 모음 템플릿을 사용할 수 있습니다. 템플릿의 목록을 확장 하는 템플릿을 선택 하 고 클릭 더하기 기호를 클릭 **새로 만들기**합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [아이콘 및 커서: 디스플레이 장치용 이미지 리소스](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [아이콘 및 커서: 디스플레이 장치용 이미지 리소스](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)