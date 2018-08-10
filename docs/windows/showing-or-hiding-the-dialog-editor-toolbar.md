---
title: 표시 하거나 대화 상자 편집기 도구 모음을 숨기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog editor, showing or hiding toolbar
ms.assetid: 93c255e1-90eb-48b6-8602-450acda75bed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a8a19de393e7451f045d840552127743f87e00ba
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019175"
---
# <a name="showing-or-hiding-the-dialog-editor-toolbar"></a>대화 상자 편집기 도구 모음 표시 또는 숨기기
열면 합니다 **대화 상자** 편집기는 **대화 상자 편집기** 솔루션의 맨 위에 있는 도구 모음이 자동으로 나타납니다.  
  
### <a name="dialog-editor-toolbar"></a>대화 상자 편집기 도구 모음  
  
|아이콘|의미|아이콘|의미|  
|----------|-------------|----------|-------------|  
|![테스트 대화 상자 단추](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|대화 상자 테스트|![전체 공간 단추](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|옆으로|  
|![왼쪽 맞춤 단추](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|왼쪽 맞춤|![아래 공간 단추](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|아래로|  
|![오른쪽 맞춤 단추](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|오른쪽 맞춤|![확인 같은 너비로 단추](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|같은 너비로|  
|![위쪽 맞춤 단추](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|위쪽 맞춤|![확인 같은 높이로 단추](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|같은 높이로|  
|![아래쪽 맞춤 단추](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|아래쪽 맞춤|![확인 같은 크기로 단추](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|같은 크기로|  
|![세로 가운데 단추](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|세로|![눈금 단추를 토글](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|모눈 설정/해제|  
|![가로 가운데 단추](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|가로|![안내선 설정/해제 단추](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|안내선 설정/해제|  
  
 합니다 **대화 상자 편집기** 도구 모음 단추가 대화 상자에서 예를 들어 크기 및 맞춤에서 컨트롤의 레이아웃을 정렬 합니다. **대화 상자 편집기** 도구 모음 단추에 명령에 해당 합니다 **형식** 메뉴. 자세한 내용은 참조 하세요 [대화 상자 편집기의 액셀러레이터 키](../windows/accelerator-keys-for-the-dialog-editor.md)합니다.  
  
 있는 경우는 **대화 상자** 편집기의 표시를 전환할 수 있습니다는 **대화 상자 편집기** 사용할 수 있는 도구 모음 및 창 목록에서 선택 하 여 도구 모음입니다.  
  
### <a name="to-show-or-hide-the-dialog-editor-toolbar"></a>표시 하거나 대화 상자 편집기 도구 모음을 숨기려면  
  
1.  에 **뷰** 메뉴 **도구 모음** 선택한 **대화 상자 편집기** 하위 메뉴에서.  
  
    > [!NOTE]
    >  합니다 **대화 상자 편집기** 도구 모음에서 대화 상자 편집기 대화 상자 리소스를 열면 기본적으로 표시 됩니다; 그러나 도구 모음을 명시적으로 닫으면 해야 대화 상자 리소스를 열면 다음에 호출 됩니다.  
  
 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework Developer's Guide*합니다. 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화 관리 되는 앱의 리소스에 대 한 내용은 참조 하세요 [Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자에 컨트롤 배치](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [방법: 리소스 만들기](../windows/how-to-create-a-resource.md)   
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [대화 상자 편집기](../windows/dialog-editor.md)