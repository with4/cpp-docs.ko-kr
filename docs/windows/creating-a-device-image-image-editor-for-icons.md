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
ms.openlocfilehash: d8fc1ce4bd5a6e125ece7461d100950f255dee44
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873227"
---
# <a name="creating-a-device-image-image-editor-for-icons"></a>장치 이미지 만들기(아이콘에 대한 이미지 편집기)
특정 스타일 (32 × 32, 아이콘에 대 한 16 색과 32 × 32, 커서 흑백) 이미지를 먼저 만듭니다 새 아이콘이 나 커서 리소스, 이미지를 만들 때 편집기. 그런 다음 초기 아이콘이 나 커서에 다양 한 크기 및 스타일에 이미지를 추가 및 다른 디스플레이 장치에 대 한 필요에 따라 각 추가 이미지를 편집할 수 있습니다. 또한 기존 이미지 형식에서 또는 그래픽 프로그램에서 만든 비트맵에서의 잘라내기 및 붙여넣기 작업을 수행 하 여 이미지를 편집할 수 있습니다.  
  
 리소스 아이콘 또는 커서를 열 때는 [이미지 편집기](../windows/image-editor-for-icons.md), 이미지 대부분 밀접 하 게 현재 디스플레이 장치는 기본적으로 열립니다.  
  
### <a name="to-create-a-new-icon-or-cursor"></a>새 아이콘 또는 커서를 만들려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md),.rc 파일을 마우스 오른쪽 단추로 클릭 한 다음 선택 **리소스 삽입** 바로 가기 메뉴에서. (단추로 하기만 하면 cursor와 같은.rc 파일에 기존 이미지 리소스를 이미 있는 경우는 **커서** 폴더와 선택 **커서 삽입** 바로 가기 메뉴에서.)  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  에 [리소스 삽입 대화 상자](../windows/add-resource-dialog-box.md)선택, **아이콘** 또는 **커서** 클릭 **새로**합니다. 아이콘의 경우 32, 32 × 16 색 아이콘 포함 아이콘 리소스를 만듭니다. 커서의 경우 32 × 32 단색 (2-색) 이미지가 생성 됩니다.  
  
     더하기 기호 (**+**) 옆에서 이미지 리소스 종류에 표시는 **리소스 삽입** 대화 상자, 도구 모음 템플릿이 있습니다 사용할 수 있습니다. 템플릿의 목록을 확장, 서식 파일을 선택 하 고 클릭를 더하기 기호를 클릭 **새로**합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 **요구 사항**  
  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [아이콘 및 커서: 디스플레이 장치용 이미지 리소스](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [액셀러레이터 키](../windows/accelerator-keys-image-editor-for-icons.md)   
 [아이콘 및 커서: 디스플레이 장치용 이미지 리소스](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)
