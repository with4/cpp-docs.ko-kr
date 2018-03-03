---
title: "표시 또는 숨기기 대화 상자 편집기 도구 모음 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog editor, showing or hiding toolbar
ms.assetid: 93c255e1-90eb-48b6-8602-450acda75bed
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dbb77c6851b9e8b93c1b3bbd0b1d30bcf65e3d42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="showing-or-hiding-the-dialog-editor-toolbar"></a>대화 상자 편집기 도구 모음 표시 또는 숨기기
대화 상자 편집기를 열려면 대화 상자 편집기 도구 모음에서 자동으로 솔루션의 위쪽에 나타납니다.  
  
### <a name="dialog-editor-toolbar"></a>대화 상자 편집기 도구 모음  
  
|아이콘|의미|아이콘|의미|  
|----------|-------------|----------|-------------|  
|![테스트 대화 상자 단추](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|대화 상자 테스트|![전체 공간 단추](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|옆으로|  
|![왼쪽 맞춤 단추](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|왼쪽 맞춤|![아래 공간 단추](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|아래로|  
|![오른쪽 맞춤 단추](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|오른쪽 맞춤|![같은 너비로 단추 만들기](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|같은 너비로|  
|![위쪽 맞춤 단추](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|위쪽 맞춤|![같은 높이로 단추 만들기](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|같은 높이로|  
|![아래쪽 맞춤 단추](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|아래쪽 맞춤|![같은 크기로 단추 만들기](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|같은 크기로|  
|![세로 가운데 단추](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|세로|![토글 단추를 모눈](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|모눈 설정/해제|  
|![가로 가운데 단추](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|가로|![안내선 설정/해제 단추](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|안내선 설정/해제|  
  
 대화 상자 편집기 도구 모음을 사용 하면 예를 들어, 크기 및 맞춤 대화 상자에서 컨트롤의 레이아웃을 정렬 하기 위한 단추가 있습니다. 대화 상자 편집기 도구 모음 단추 서식 메뉴 명령에 해당합니다. 자세한 내용은 참조 [대화 상자 편집기의 액셀러레이터 키](../windows/accelerator-keys-for-the-dialog-editor.md)합니다.  
  
 대화 상자 편집기에 있는 경우에 사용 가능한 도구 모음 및 창의 목록에서 선택 하 여 대화 상자 편집기 도구 모음을 표시를 전환할 수 있습니다.  
  
### <a name="to-show-or-hide-the-dialog-editor-toolbar"></a>표시 하거나 대화 상자 편집기 도구 모음을 숨기려면  
  
1.  에 **보기** 메뉴 클릭 **도구 모음** 선택 **대화 상자 편집기** 하위 메뉴에서 합니다.  
  
    > [!NOTE]
    >  대화 상자 편집기 도구 모음; 대화 상자 편집기에서 대화 상자 리소스를 열 때 기본적으로 표시 됩니다. 그러나 명시적으로 도구 모음을 닫은 경우 다음에 대화 상자 리소스를 열 때 호출 해야 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자에 컨트롤 배치](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [방법: 리소스 만들기](../windows/how-to-create-a-resource.md)   
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [대화 상자 편집기](../windows/dialog-editor.md)

