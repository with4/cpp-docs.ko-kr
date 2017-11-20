---
title: "새 도구 모음 단추 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.toolbar
dev_langs: C++
helpviewer_keywords:
- Toolbar editor, creating buttons
- toolbar buttons (in Toolbar editor), button image
- toolbar buttons (in Toolbar editor), creating
- toolbar buttons (in Toolbar editor)
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 340756fcb85af8402f3c01d9efb8f1c62c6b0b41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-new-toolbar-button"></a>새 도구 모음 단추 만들기
### <a name="to-create-a-new-toolbar-button"></a>새 도구 모음 단추를 만들려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md) 리소스 폴더 (예: Project1.rc)를 확장 합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  확장 된 **도구 모음** 폴더를 편집 하려면 도구 모음을 선택 합니다.  
  
3.  도구 모음의 오른쪽 끝에 빈 단추에 ID를 지정 합니다. 편집 하 여 그렇게 할 수는 **ID** 속성에는 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 예를 들어 다음 도구 모음 단추 메뉴 옵션으로 동일한 ID를 제공 하는 것이 좋습니다. 이 경우 드롭다운 목록 상자를 사용 하 여 선택 하 고 **ID** 메뉴 옵션입니다.  
  
     또는  
  
     도구 모음 보기 창에서 도구 모음의 오른쪽 끝에 빈 단추를 선택 하 고 그리기를 시작 합니다. 기본 단추 명령 ID가 할당 됩니다 (ID_BUTTON\<n >).  
  
 복사 하 고 새 단추 여 도구 모음 이미지를 붙여도 합니다.  
  
#### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>도구 모음에 단추로 이미지를 추가 하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md)를 두 번 클릭 하 여 도구 모음을 엽니다.  
  
2.  다음으로, 도구 모음에 추가 하려면 원하는 이미지를 엽니다.  
  
    > [!NOTE]
    >  Visual Studio에서 이미지를 열 이미지 편집기에서 열립니다. 다른 그래픽 프로그램에서 이미지를 열 수도 있습니다.  
  
3.  **편집** 메뉴 선택 **복사**합니다.  
  
4.  소스 창 맨 위에 있는 탭을 클릭 하 여 도구 모음으로 전환 합니다.  
  
5.  **편집** 메뉴 선택 **붙여넣기**합니다.  
  
     이미지에 새 단추로 도구 모음에 표시 됩니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](https://msdn.microsoft.com/library/f45fce5x.aspx) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](https://msdn.microsoft.com/library/xbx3z216.aspx)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](https://msdn.microsoft.com/library/h6270d0z.aspx)합니다.  
  
### <a name="requirements"></a>요구 사항  
 MFC 또는 ATL  
  
## <a name="see-also"></a>참고 항목  
 [도구 모음 단추 속성](../windows/toolbar-button-properties.md)   
 [만들기, 이동 및 편집 도구 모음 단추](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [도구 모음 편집기](../windows/toolbar-editor.md)

