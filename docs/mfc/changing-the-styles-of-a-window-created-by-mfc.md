---
title: MFC에서 만든 창 스타일 변경 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window styles [MFC]
- WS_OVERLAPPEDWINDOW macro [MFC]
- single document interface (SDI), changing window attributes
- MDI [MFC], window styles
- windows [MFC], MFC
- child windows [MFC], styles
- MFC, windows
- CFrameWnd class [MFC], window styles
- CREATESTRUCT macro [MFC]
- CMDIChildWnd class [MFC], changing window styles
- multidocument interface style
- PreCreateWindow method [MFC], window styles
- single document interface (SDI), style
- default window style
- defaults [MFC], window style
- PreCreateWindow method [MFC], changing window styles
- CMainFrame class [MFC]
- styles [MFC], windows
ms.assetid: 77fa4f03-96b4-4687-9ade-41e46f7e4b0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34ea35bd43e2bf4e96cbc1552ff169789c1068a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC에서 만든 창 스타일 변경
해당 버전에는 `WinMain` 함수, MFC 있습니다에 대 한 몇 가지 표준 창 클래스를 등록 합니다. MFC의 일반적으로 편집 하지 않은 때문에 `WinMain`는 함수를 사용 하면 MFC 기본 창 스타일을 변경할 수 없도록 합니다. 이 문서에서는 기존 응용 프로그램에서 이러한 미리 등록된 창 클래스 스타일을 변경 하는 방법을 설명 합니다.  
  
##  <a name="_core_changing_styles_in_a_new_mfc_application"></a> 새 MFC 응용 프로그램에 대 한 스타일 변경  
 Visual c + + 2.0 이상을 사용 하 여, 응용 프로그램을 만들 때 응용 프로그램 마법사에서 기본 창 스타일을 변경할 수 있습니다. 응용 프로그램 마법사의 사용자 인터페이스 기능 페이지를 주 프레임 창 및 MDI 자식 창에 대 한 스타일을 변경할 수 있습니다. 창 유형 중 하나에 대 한 프레임 두께 (굵은 또는)를 지정할 수 있습니다 및 다음 중 하나입니다.  
  
-   창의는 최소화 나 최대화 컨트롤 있는지 여부.  
  
-   여부 창이 표시 되는 처음 최소화, 최대화 하거나 둘 다 합니다.  
  
 주 프레임 창의 창이 시스템 메뉴에 있는지 여부를 지정할 수 있습니다. MDI 자식 창, 창에서 분할자 창을 지원 하는지 여부를 지정할 수 있습니다.  
  
##  <a name="_core_changing_styles_in_an_existing_application"></a> 기존 응용 프로그램에 대 한 스타일 변경  
 기존 응용 프로그램 창의 특성을 변경 하는 경우 대신이 문서의 나머지 부분의 지시를 따릅니다.  
  
 응용 프로그램 마법사를 사용 하 여 만든 응용 프로그램 프레임 워크에 의해 사용 되는 기본 창 특성을 변경 하려면 재정의 창의 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) 가상 멤버 함수입니다. `PreCreateWindow` 통해 응용 프로그램에서 일반적으로 내부적으로 관리 하 여 만들기 프로세스를 액세스 하는 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) 클래스입니다. 프레임 워크를 호출 하 여 `PreCreateWindow` 창을 만드는 직전 합니다. 수정 하 여는 [CREATESTRUCT](../mfc/reference/createstruct-structure.md) 에 전달 하는 구조 `PreCreateWindow`, 응용 프로그램 창을 만들기 위해 사용 되는 특성을 변경할 수 있습니다. 예를 들어 창의 캡션을 사용 하 여 사용 하지 않습니다을 보장 하려면 다음과 같은 연산을 사용 합니다.  
  
 [!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]  
  
 [CTRLBARS](../visual-cpp-samples.md) 샘플 응용 프로그램에 창 특성 변경에 대 한이 기술을 보여 줍니다. 변경 응용 프로그램에 따라 `PreCreateWindow`, 함수의 기본 클래스 구현을 호출 해야 합니다.  
  
 SDI 사례에 대해 다음 설명 및 [MDI 대/소문자](#_core_the_mdi_case)합니다.  
  
##  <a name="_core_the_sdi_case"></a> SDI 대/소문자  
 단일 문서 SDI (인터페이스) 응용 프로그램 프레임 워크의 기본 창 스타일은의 조합 된 **WS_OVERLAPPEDWINDOW** 및 **FWS_ADDTOTITLE** 스타일입니다. **FWS_ADDTOTITLE** 창 캡션에 문서 제목을 추가 하기 위해 프레임 워크에 지시 하는 MFC 관련 스타일입니다. SDI 응용 프로그램에서 창의 특성을 변경 하려면 재정의 `PreCreateWindow` 에서 파생 된 클래스에는 함수 `CFrameWnd` (있는 응용 프로그램 마법사 이름 `CMainFrame`). 예를 들어:  
  
 [!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]  
  
 이 코드는 최소화 및 최대화 단추 및 크기 조정 가능한 테두리 없이 주 프레임 창을 만듭니다. 창 가운데 처음 화면에 표시 됩니다.  
  
##  <a name="_core_the_mdi_case"></a> MDI 대/소문자  
 다중 문서 MDI (인터페이스) 응용 프로그램에서 자식 창의 창 스타일을 변경 하려면 약간 더 많은 작업이 필요 합니다. 기본적으로 응용 프로그램 마법사를 사용 하 여 만든 MDI 응용 프로그램이 사용 하 여 기본 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) MFC에 정의 된 클래스입니다. MDI 자식 창의 창 스타일을 변경 하려면에서 새 클래스를 파생 시켜야 합니다 `CMDIChildWnd` 및 바꾸기에 대 한 모든 참조 `CMDIChildWnd` 새 클래스에 대 한 참조를 사용 하 여 프로젝트에 있습니다. 대부분의 경우 유일한에 대 한 참조 `CMDIChildWnd` 응용 프로그램에서 응용 프로그램에 있는 `InitInstance` 멤버 함수입니다.  
  
 MDI 응용 프로그램에서 사용 되는 기본 창 스타일은의 조합 된 **WS_CHILD**, **WS_OVERLAPPEDWINDOW**, 및 **FWS_ADDTOTITLE** 스타일입니다. MDI 응용 프로그램의 자식 창의 창 특성을 변경 하려면 재정의 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) 에서 파생 된 클래스에는 함수 `CMDIChildWnd`합니다. 예를 들어:  
  
 [!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]  
  
 이 코드는 MDI 자식 최대화 단추 없이 창을 만듭니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [창 스타일](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
-   [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)  
  
-   [창 스타일](http://msdn.microsoft.com/library/windows/desktop/ms632600)  
  
## <a name="see-also"></a>참고 항목  
 [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)

