---
title: "비트맵을 도구 모음으로 변환 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- bitmaps [C++], converting to toolbars
- Toolbar editor, converting bitmaps
- toolbars [C++], converting bitmaps
ms.assetid: 971c181b-40f5-44be-843d-677a7c235667
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d189395bbedff4d73cc690d454ddd07af4d109e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="converting-bitmaps-to-toolbars"></a>비트맵을 도구 모음으로 변환
새 도구 모음 비트맵을 변환 하 여 만들 수 있습니다. 비트맵의 그래픽 도구 모음에 대 한 단추 이미지를 변환합니다. 일반적으로 비트맵 각 단추에 대 한 이미지를 사용 하 여 하나의 비트맵에 여러 단추 이미지를 포함합니다. 이미지는 크기에 제한이; 있을 수 있습니다. 기본값이 16 픽셀 너비와 이미지의 높이입니다. 에 단추 이미지의 크기를 지정할 수 있습니다는 [새 도구 모음 리소스 대화 상자](../windows/new-toolbar-resource-dialog-box.md) 에서 도구 모음 편집기를 선택 하는 경우는 **이미지** 이미지 편집기 메뉴.  
  
### <a name="to-convert-bitmaps-to-a-toolbar"></a>비트맵을 도구 모음으로 변환 하려면  
  
1.  기존 비트맵 리소스를 열기 고 [이미지 편집기](../windows/image-editor-for-icons.md)합니다. (비트맵은.rc 파일에 들어 있지.rc 파일을 마우스 오른쪽 단추로 클릭을 선택 **가져오기** 바로 가기 메뉴에서.rc 파일에 추가 하려는 비트맵 문서로 이동한 다음 클릭 **열려**.)  
  
2.  **이미지** 메뉴 선택 **도구 모음 편집기**합니다.  
  
     [새 도구 모음 리소스 대화 상자](../windows/new-toolbar-resource-dialog-box.md) 나타납니다. 비트맵에 맞게 아이콘 이미지의 높이 너비를 변경할 수 있습니다. 도구 모음 편집기에서 도구 모음 이미지가 표시 됩니다.  
  
3.  변환을 완료 하려면 명령을 변경 **ID** 사용 하 여 단추는 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 새 입력 **ID** 선택 또는 **ID** 드롭 다운 목록에서 합니다.  
  
    > [!TIP]
    >  속성 창 제목 표시줄에 압정 단추를 포함합니다. 이 단추를 클릭 하거나 창의 자동 숨기기를 해제 합니다. 각 속성 창을 다시 열지 않고 모든 도구 모음 단추 속성 간에 신속 하 게 전환, 해제 자동 숨기기 속성 창이 고정 되므로 합니다.  
  
 사용 하 여 새 도구 모음 단추의 명령 Id를 변경할 수도 있습니다는 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 새 도구 모음 편집에 대 한 자세한 내용은 참조 하십시오. [만들기, 이동 및 편집 도구 모음 단추](../windows/creating-moving-and-editing-toolbar-buttons.md)합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 요구 사항  
  
 MFC 또는 ATL  
  
## <a name="see-also"></a>참고 항목  
 [새 도구 모음 만들기](../windows/creating-new-toolbars.md)   
 [도구 모음 편집기](../windows/toolbar-editor.md)

