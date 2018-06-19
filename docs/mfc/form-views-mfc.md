---
title: 폼 뷰 (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user interfaces [MFC], forms
- forms [MFC]
- applications [MFC], forms-based
- forms-based applications [MFC]
- forms [MFC], adding to applications
ms.assetid: efbe73c1-4ca4-4613-aac2-30d916e92c0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87775c8afa1fa6eec8fbbdbbaa11bc9b5e6f1faa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349051"
---
# <a name="form-views-mfc"></a>폼 뷰(MFC)
Visual c + + 응용 프로그램을 지 원하는 비롯 한 MFC 라이브러리에 폼을 추가할 수 있습니다는 [폼 기반 응용 프로그램](../mfc/reference/creating-a-forms-based-mfc-application.md) (해당 뷰 클래스에서 파생 된 하나 `CFormView`). 폼을 지 원하는 응용 프로그램를 처음 만들지 않은 경우 Visual c + + 새 폼을 삽입 하는 경우이 지원 기능을 추가 합니다. 기본값을 구현 하는 SDI 또는 MDI 응용 프로그램에서 [문서/뷰 아키텍처](../mfc/document-view-architecture.md)선택 하면는 `New` 명령 (기본적으로에 **파일** 메뉴), Visual c + + 사용자에 게 사용 가능한 폼에서 선택 합니다.  
  
 SDI 응용 프로그램 사용자가 선택 된 `New` 명령, 폼의 현재 인스턴스 계속 실행 되지만 선택한 폼을 응용 프로그램의 새 인스턴스를 찾지 하는 경우에 생성 됩니다. MDI 응용 프로그램에서 폼의 현재 인스턴스 계속 실행 사용자가 선택 된 `New` 명령입니다.  
  
> [!NOTE]
>  대화 상자 기반 응용 프로그램에 폼을 삽입할 수 있습니다 (대화 상자 클래스가 기반 `CDialog` 없습니다 보기에서 클래스가 구현 되는 하나). 그러나 문서/뷰 아키텍처 없이 Visual c + + 구현 하지 않는 자동으로 **파일**&#124;**새로** 기능입니다. 사용자가 다양 한 속성 페이지로 구성 된 대화 상자를 구현 하 여과 같은 다른 폼을 볼 수 있는 방법을 만들어야 합니다.  
  
 응용 프로그램에 새 폼을 삽입 하는 경우 Visual c + +는 다음을 수행 합니다.  
  
-   선택한 양식 스타일 클래스 중 하나를 기반으로 클래스를 만듭니다 (`CFormView`, `CRecordView`, `CDaoRecordView`, 또는 `CDialog`).  
  
-   적절 한 스타일으로 대화 상자 리소스를 만듭니다 (또는 아직으로 클래스와 연결 되지 않은 기존 대화 상자 리소스를 사용할 수 있습니다).  
  
     기존 대화 상자 리소스를 선택 하면 대화 상자에 대 한 속성 페이지를 사용 하 여 이러한 스타일을 설정 해야 합니다. 대화 상자에 대 한 스타일을 포함 해야 합니다.  
  
     **WS_CHILD**= On  
  
     `WS_BORDER`= 해제  
  
     **WS_VISIBLE**= Off  
  
     **WS_CAPTION =** 해제  
  
 문서/뷰 아키텍처를 기반으로 응용 프로그램에 대 한는 **새 양식을** 명령 (클래스 뷰에서 마우스 오른쪽 단추 클릭)도 있습니다.  
  
-   만듭니다는 **CDocument**-기반 클래스  
  
     만든 새 클래스를 대신 사용할 수 있습니다 기존 **CDocument**-프로젝트의 클래스를 기반으로 합니다.  
  
-   문서 템플릿 (에서 파생 된 **CDocument**) 문자열, 메뉴 및 아이콘 리소스입니다.  
  
     템플릿을 기반으로 사용할 새 클래스를 만들 수 있습니다.  
  
-   에 대 한 호출 추가 **AddDocumentTemplate** 응용 프로그램에서 `InitInstance` 코드입니다.  
  
     선택 하면 사용 가능한 폼의 목록에 폼을 추가 하는 각 새 폼을 만들에 대 한이 코드를 추가 하는 visual c + +는 `New` 명령입니다. 이 코드는 폼의 관련된 리소스 ID와 연결 된 문서, 뷰 및 새 폼 개체를 구성 하는 프레임 클래스의 이름이 포함 됩니다.  
  
     문서 템플릿의 문서, 프레임 창 및 뷰 사이의 연결으로 사용입니다. 단일 문서에 대 한 다양 한 템플릿을 만들 수 있습니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [폼 기반 응용 프로그램 만들기](../mfc/reference/creating-a-forms-based-mfc-application.md)  
  
-   [프로젝트에 폼 삽입](../mfc/inserting-a-form-into-a-project.md)  
  
## <a name="see-also"></a>참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
