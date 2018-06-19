---
title: 파일 탐색기 스타일 MFC 응용 프로그램 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcexplorer.project
dev_langs:
- C++
helpviewer_keywords:
- browsers [MFC], Explorer-style applications
- MFC applications [MFC], Windows Explorer-style
- Explorer-style applications [MFC], creating
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5b0f5d4bdabc987d4f4177f616ce756c351b8b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370157"
---
# <a name="creating-a-file-explorer-style-mfc-application"></a>파일 탐색기 스타일 MFC 응용 프로그램 만들기
파일 탐색기에 대 한 사용자 인터페이스 (UI)를 사용 하는 많은 Windows 시스템 응용 프로그램. 예를 들어, 파일 탐색기를 시작 하면 응용 프로그램을 수직 분할 분할 막대 클라이언트 영역을 표시 됩니다. 클라이언트 영역의 오른쪽 세부 정보를 표시 선택한 항목과 관련 된 왼쪽된 창에서 및 클라이언트 영역의 왼쪽 탐색 및 검색 기능을 제공 합니다. 사용자가 왼쪽된 창에서 항목을 응용 프로그램에 오른쪽 창을 다시 채워집니다. MDI 응용 프로그램에서 명령을 사용할 수는 **보기** 메뉴 오른쪽 창에 표시 되는 세부의 크기를 변경할 수 있습니다. (SDI 또는 다중 최상위 문서 응용 프로그램에서 변경할 수 있습니다만 도구 모음 단추를 사용 하 여 세부 정보.)  
  
 창 내용은 응용 프로그램에 따라 달라 집니다. 파일 시스템 브라우저의 왼쪽된 창 오른쪽 창에는 폴더, 개별 파일 또는 컴퓨터 및 세부 정보 표시 하는 동안 디렉터리 또는 컴퓨터나 컴퓨터 그룹의 계층 뷰를 보여 줍니다. 내용을 반드시 파일 되도록 합니다. 전자 메일 메시지, 오류 보고서, 또는 데이터베이스의 다른 항목 수 있습니다.  
  
 마법사는 다음 클래스에서:  
  
-   **CLeftView** 클라이언트 영역의 왼쪽된 창 클래스를 정의 합니다. 파생 된 항상 [CTreeView](../../mfc/reference/ctreeview-class.md)합니다.  
  
-   C*ProjName*뷰 클래스 오른쪽 창의 클라이언트 영역을 정의 합니다. 파생 된 기본적으로 [CListView](../../mfc/reference/clistview-class.md) 보기에서 지정 하는 클래스에 따라 다른 유형의 가능 하지만 **기본 클래스** 목록에 [생성 된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md) 의 페이지는 마법사입니다.  
  
 생성 된 응용 프로그램 (SDI)는 단일 문서 인터페이스, 다중 문서 인터페이스 mdi (다중) 또는 다중 최상위 문서 아키텍처 있을 수 있습니다. 사용 하는 응용 프로그램에서 각 프레임 창으로 분할할 [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)합니다. 이 응용 프로그램 종류를 코딩 하는 것이 유형의 응용 프로그램에는 각 분할자 창 내에서 별도 컨트롤 뷰는 점을 제외 하 고 분할자를 사용 하는 일반적인 MFC 응용 프로그램을 코딩 하는 것과 비슷합니다.  
  
 오른쪽 창에서 기본 목록 보기를 사용 하는 경우 마법사 보기의 스타일을 큰 아이콘, 작은 아이콘, 목록 및 자세히 모드 사이에서 전환 하려면 (MDI 응용 프로그램 전용)에서 선택할 수 있는 추가 메뉴 및 도구 모음 단추를 만듭니다.  
  
### <a name="to-begin-creating-a-file-explorer-style-mfc-executable"></a>파일 탐색기 스타일 MFC 실행 파일 만들기를 시작 하려면  
  
1.  지시에 따라 [MFC 응용 프로그램을 만드는](../../mfc/reference/creating-an-mfc-application.md)합니다.  
  
2.  MFC 응용 프로그램 마법사에서 [응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) 선택 페이지는 **파일 탐색기** 프로젝트 스타일입니다.  
  
3.  마법사의 나머지 페이지에서 원하는 다른 옵션을 설정 합니다.  
  
4.  클릭 **마침** 기본 응용 프로그램을 생성 합니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [여러 문서 형식, 뷰 및 프레임 창](../../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [파생 된 뷰 클래스](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [응용 프로그램 디자인 선택](../../mfc/application-design-choices.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)   
 [웹 브라우저 스타일 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)   
 [폼 기반 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-forms-based-mfc-application.md)

