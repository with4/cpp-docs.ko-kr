---
title: '예: 메뉴 명령을 통해 대화 상자를 표시 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20d355215388861a7bc2586c2c253cd551124809
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347989"
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>예: 메뉴 명령을 통해 대화 상자 표시
이 항목에서는 프로시저를:  
  
-   메뉴 명령을 통해 모달 대화 상자를 표시 합니다.  
  
-   메뉴 명령을 통해 모덜리스 대화 상자를 표시 합니다.  
  
 두 샘플 절차 MFC 응용 프로그램에 적용 되며으로 만들면 응용 프로그램에서 작동할지는 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)합니다.  
  
 절차는 다음 이름 및 값을 사용합니다.  
  
|항목|이름 또는 값|  
|----------|-------------------|  
|응용 프로그램|DisplayDialog|  
|메뉴 명령|테스트; 보기 메뉴 명령 명령 ID ID_VIEW_TEST =|  
|대화 상자|테스트 대화 상자 클래스 CTestDialog; = 헤더 파일 TestDialog.h; = 변수 testdlg, ptestdlg =|  
|명령 처리기|OnViewTest|  
  
### <a name="to-display-a-modal-dialog-box"></a>모달 대화 상자를 표시 하려면  
  
1.  메뉴 명령; 만들기 참조 [만들기 메뉴 또는 메뉴 항목](../windows/creating-a-menu.md)합니다.  
  
2.  만들기 대화 상자. 참조 [시작 대화 상자 편집기](../windows/creating-a-new-dialog-box.md)합니다.  
  
3.  대화 상자에 대 한 클래스를 추가 합니다. 참조 [클래스 추가](../ide/adding-a-class-visual-cpp.md) 자세한 정보에 대 한 합니다.  
  
4.  **클래스 뷰**, 문서 클래스 (CDisplayDialogDoc)를 선택 합니다. **속성** 창에서 **이벤트** 단추를 클릭합니다. 왼쪽된 창에서 메뉴 명령 (ID_VIEW_TEST)의 ID를 두 번 클릭은 **속성** 창과 선택 **명령**합니다. 오른쪽 창에서 아래쪽 화살표를 클릭 하 고 선택  **\<추가 > OnViewTest**합니다.  
  
     MDI 응용 프로그램의 메인프레임에 메뉴 명령을 추가한 경우 응용 프로그램 클래스 (CDisplayDialogApp)을 대신 선택 합니다.  
  
5.  다음 include CDisplayDialogDoc.cpp (또는 CDisplayDialogApp.cpp) 문을 추가 합니다. 기존 include 문의 한 후:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
6.  다음 코드를 추가 `OnViewTest` 함수를 구현 하려면:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#43](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_2.cpp)]  
  
### <a name="to-display-a-modeless-dialog-box"></a>모덜리스 대화 상자를 표시 하려면  
  
1.  뷰 클래스 (CDisplayDialogView) 4 단계에서 선택 제외 하 고 모달 대화 상자를 표시 하는 처음 4 개 단계를 수행 합니다.  
  
2.  DisplayDialogView.h를 편집 합니다.  
  
    -   대화 상자 클래스 선언 앞에 첫 번째 클래스를 선언 합니다.  
  
         [!code-cpp[NVC_MFCControlLadenDialog#44](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_3.h)]  
  
    -   공용 속성 섹션 뒤 대화 상자에 대 한 포인터를 선언 합니다.  
  
         [!code-cpp[NVC_MFCControlLadenDialog#45](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_4.h)]  
  
3.  DisplayDialogView.cpp를 편집 합니다.  
  
    -   다음 문을 포함 후 기존 include 문을 추가 합니다.  
  
         [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
    -   생성자에 다음 코드를 추가 합니다.  
  
         [!code-cpp[NVC_MFCControlLadenDialog#46](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_5.cpp)]  
  
    -   소멸자에 다음 코드를 추가 합니다.  
  
         [!code-cpp[NVC_MFCControlLadenDialog#47](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_6.cpp)]  
  
    -   다음 코드를 추가 `OnViewTest` 함수를 구현 하려면:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#48](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_7.cpp)]  
  
 또한 다음 기술 자료 문서를 참조 하십시오.  
  
-   Q251059: 방법: MFC 대화 상자에 대 한 고유한 창 클래스 이름 제공  
  
## <a name="see-also"></a>참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [모달 및 모덜리스 대화 상자](../mfc/modal-and-modeless-dialog-boxes.md)

