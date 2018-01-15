---
title: "MFC 개체 간 관계 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ea93e9e56b676e4dfef33ecbcabfd9754458024
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="relationships-among-mfc-objects"></a>MFC 개체 간 관계
문서/뷰 만들기 프로세스를 전체적으로 배치 하려면 실행 중인 프로그램을 검토: 문서, 뷰를 포함 하는 데 사용 되는 프레임 창 및 문서에 연결 된 보기입니다.  
  
-   문서는 문서를 만든 서식 파일에 해당 문서와 대 한 뷰 목록을 유지 합니다.  
  
-   해당 문서에 대 한 포인터를 유지 뷰와 부모 프레임 창의 자식입니다.  
  
-   문서 프레임 창 현재 활성화 된 뷰에 대 한 포인터를 유지합니다.  
  
-   문서 서식 파일은 열린 문서 목록을 유지합니다.  
  
-   응용 프로그램은 문서 템플릿의 목록을 유지합니다.  
  
-   Windows는 추적 열려 있는 모든 창을 하므로 메시지를 보낼 수 있습니다.  
  
 이러한 관계는 문서/뷰를 만드는 동안 설정 됩니다. 다음 표에서 실행 중인 프로그램의 개체는 다른 개체에 액세스 하는 방법을 보여 줍니다. 모든 개체는 전역 함수를 호출 하 여 응용 프로그램 개체에 대 한 포인터를 가져올 수 [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp)합니다.  
  
### <a name="gaining-access-to-other-objects-in-your-application"></a>응용 프로그램의 다른 개체에 액세스  
  
|개체에서|다른 개체에 액세스 하는 방법|  
|-----------------|---------------------------------|  
|문서|사용 하 여 [GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) 및 [GetNextView](../mfc/reference/cdocument-class.md#getnextview) 문서의 뷰 목록에 액세스 합니다.<br /><br /> 호출 [GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate) 문서 서식 파일을 얻으려고 합니다.|  
|보기|호출 [GetDocument](../mfc/reference/cview-class.md#getdocument) 가 문서를 가져와야 합니다.<br /><br /> 호출 [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe) 프레임 창에 얻으려고 합니다.|  
|문서 프레임 창|호출 [얻을 수](../mfc/reference/cframewnd-class.md#getactiveview) 현재 볼 수 있습니다.<br /><br /> 호출 [GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument) 현재 보기에 연결 된 문서를 가져와야 합니다.|  
|MDI 프레임 창|호출 [MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive) 현재 활성 가져오려는 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)합니다.|  
  
 일반적으로 프레임 창에는 하나의 뷰만 이지만 경우에 따라 분할 창에서와 같이 동일한 프레임 창 보기가 포함 되어 있는 여러 합니다. 현재 활성 보기;에 대 한 포인터를 유지 하는 프레임 창 포인터는 다른 뷰가 활성화 될 때마다 업데이트 됩니다.  
  
> [!NOTE]
>  주 프레임 창에 대 한 포인터에 저장 되는 [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) application 개체의 멤버 변수입니다. 에 대 한 호출 `OnFileNew` 의 재정의에서 `InitInstance` 의 멤버 함수 `CWinApp` 설정 `m_pMainWnd` 드립니다. 호출 하지 않으면 `OnFileNew`에서 변수의 값을 설정 해야 `InitInstance` 직접 합니다. (SDI COM 구성 요소 (서버) 응용 프로그램 설정할 없습니다 변수 상관 명령줄에 있으면.) `m_pMainWnd` 클래스의 멤버는 이제 `CWinThread` 대신 `CWinApp`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [문서 서식 파일 만들기](../mfc/document-template-creation.md)   
 [문서/뷰 만들기](../mfc/document-view-creation.md)   
 [새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)

