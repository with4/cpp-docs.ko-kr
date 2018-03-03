---
title: "리소스 편집기에서 리소스 보기 및 편집 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.resourceview
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- rc files, viewing resources
- Resource View pane
- layouts, previewing resource
- code, viewing resources
- resource editors, viewing resources
- .rc files, viewing resources
- resources [Visual Studio], editing
ms.assetid: ba8bdc07-3f60-43c7-aa5c-d5dd11f0966e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 980264ab1857af214dcd24703980b8efa9a4d2dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="viewing-and-editing-resources-in-a-resource-editor"></a>리소스 편집기에서 리소스 보기 및 편집
각 리소스 종류에 해당 리소스 종류에 있는 리소스 편집기 있습니다. 다시 정렬 크기를 조정 하거나 컨트롤 및 기능을 추가 하지 않으면 연결된 된 편집기를 사용 하 여 리소스의 기능을 수정할 수 있습니다. 리소스를 편집할 수도 있습니다 [텍스트 형식](../windows/how-to-open-a-resource-script-file-in-text-format.md) 및 [이진 형식](../windows/opening-a-resource-for-binary-editing.md)합니다.  
  
 일부 리소스 종류는 개별 파일을 가져올 수 있으며 여러 가지 방법으로; 여기에 비트맵, 아이콘, 커서, 도구 모음 및 html 파일이 포함 됩니다. 이러한 리소스에는 파일 이름으로 [리소스 식별자](../windows/symbols-resource-identifiers.md)합니다. 다른 사용자에 게 대화 상자, 메뉴 및 Win32 프로젝트에 있는 문자열 테이블 등 존재 리소스 스크립트 (.rc) 파일 또는 리소스 템플릿 (.rct) 파일의 일부로 합니다.  
  
> [!NOTE]
>  리소스의 속성 [속성 창을 사용 하 여 수정할 수](../windows/changing-the-properties-of-a-resource.md)합니다.  
  
## <a name="win32-resources"></a>Win32 리소스  
 Win32 리소스에 액세스할 수 있습니다는 [리소스 뷰](../windows/resource-view-window.md) 창.  
  
#### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>리소스 편집기에서 Win32 리소스를 보려면  
  
1.  선택 **리소스 뷰** 에서 **보기** 메뉴.  
  
2.  리소스 뷰 창에서 최상위 창 없는 경우 클릭는 **리소스 뷰** 탭에는 맨 위로 이동 합니다.  
  
3.  리소스 보기에서 보려는 리소스를 포함 하는 프로젝트에 대 한 폴더를 확장 합니다. 예를 들어 대화 상자 리소스를 보려는 경우 대화 상자 폴더를 확장 합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
4.  예를 들어 IDD_ABOUTBOX 리소스를 두 번 클릭 합니다.  
  
     리소스가 해당 편집기에서 열립니다. 예를 들어 대화 상자 리소스에 대 한 리소스 대화 상자 편집기에서 열립니다.  
  
     수도 있습니다 [프로젝트를 열지 않고도 (리소스 스크립트).rc 파일에서 리소스를 볼](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)합니다.  
  
#### <a name="to-delete-an-existing-win-32-resource"></a>기존 win32 리소스를 삭제 하려면  
  
1.  리소스 뷰에서 리소스 유형에 대 한 노드를 확장 합니다.  
  
2.  삭제 하 고 선택 하려면 리소스를 마우스 오른쪽 단추로 클릭 **삭제** 바로 가기 메뉴에서.  
  
    > [!NOTE]
    >  .Rc 파일이 프로젝트 외부 문서 창에 열려 있는 경우 동일한 바로 가기 메뉴 명령을 사용 하 여 리소스를 삭제할 수 있습니다.  
  
## <a name="resources-in-managed-projects"></a>관리 되는 프로젝트의 리소스  
 리소스 스크립트 파일을 사용 하지 않는 관리 되는 프로젝트에서 리소스를 열어야 **솔루션 탐색기**합니다. 관리되는 프로젝트에서 리소스 파일로 작업하려면 [이미지 편집기](../windows/image-editor-for-icons.md) 및 [바이너리 편집기](binary-editor.md) 를 사용할 수 있습니다. 편집할 관리되는 리소스는 연결된 리소스여야 합니다. Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
#### <a name="to-view-a-managed-resource-in-a-resource-editor"></a>리소스 편집기에서 관리 되는 리소스를 보려면  
  
1.  솔루션 탐색기에서 예를 들어 Bitmap1.bmp 리소스를 두 번 클릭 합니다.  
  
     리소스가 해당 편집기에서 열립니다.  
  
#### <a name="to-delete-an-existing-managed-resource"></a>기존 관리 되는 리소스를 삭제 하려면  
  
1.  솔루션 탐색기에서 삭제 하 고 선택 하려면 리소스를 마우스 오른쪽 단추로 **삭제** 바로 가기 메뉴에서.  
  
### <a name="requirements"></a>요구 사항  
 없음  
  
## <a name="see-also"></a>참고 항목  
 [리소스 편집기](../windows/resource-editors.md)

