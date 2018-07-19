---
title: 코드 보기 (데이터 액세스) 응용 프로그램 마법사로 만든 기록 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application wizards [C++], record view code
- record views, refreshing controls
- record views, application wizard code
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 15355d156b3c85c8f99ba638b30f831da96686af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33107105"
---
# <a name="record-view-code-created-by-application-wizard--mfc-data-access"></a>응용 프로그램 마법사가 만든 레코드 뷰 코드  (MFC Data Access)
[MFC 응용 프로그램 마법사](../mfc/reference/database-support-mfc-application-wizard.md) 재정의 보기의 `OnInitialUpdate` 및 `OnGetRecordset` 멤버 함수입니다. 프레임워크는 프레임 창, 문서 및 뷰를 만든 후 `OnInitialUpdate`를 호출하여 뷰를 초기화합니다. `OnInitialUpdate`는 문서에서 레코드 집합에 대한 포인터를 가져옵니다. 기본 클래스에 대 한 호출 [cview:: Oninitialupdate](../mfc/reference/cview-class.md#oninitialupdate) 기능은 레코드 집합을 엽니다. 다음 코드에서는이 프로세스에 대 한는 `CRecordView`:  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
 레코드 집합이 열리면 레코드를 선택합니다. [Crecordset:: Open](../mfc/reference/crecordset-class.md#open) 현재 레코드와 DDX 이동 데이터를 레코드 집합의 필드 데이터 멤버에 해당 요소에 폼 컨트롤 보기에서 첫 번째 레코드를 만듭니다. RFX에 대 한 자세한 내용은 참조 [Exchange RFX (레코드 필드)](../data/odbc/record-field-exchange-rfx.md)합니다. DDX에 대 한 자세한 내용은 참조 [대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)합니다. 문서/뷰 만들기 프로세스에 대 한 정보를 참조 하십시오. [클래스를 사용 하 여 Windows 용 응용 프로그램을](../mfc/using-the-classes-to-write-applications-for-windows.md)합니다.  
  
> [!NOTE]
>  최종 사용자가 레코드 집합에서의 레코드 뷰 컨트롤을 새로 고치는 기능을 제공해야 합니다. 이 기능을 제공하지 않는 경우 사용자가 컨트롤 값을 잘못된 값으로 변경하면 현재 레코드에서 영구적으로 작업이 중지될 수 있습니다. 호출 컨트롤을 새로 고치려면는 `CWnd` 멤버 함수 [UpdateData](../mfc/reference/cwnd-class.md#updatedata) 의 매개 변수와 함께 **FALSE**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 뷰 사용](../data/using-a-record-view-mfc-data-access.md)