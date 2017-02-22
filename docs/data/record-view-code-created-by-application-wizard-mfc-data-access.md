---
title: "응용 프로그램 마법사가 만든 레코드 뷰 코드  (MFC Data Access) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 마법사[C++], 레코드 뷰 코드"
  - "레코드 뷰, 응용 프로그램 마법사 코드"
  - "레코드 뷰, 컨트롤 새로 고침"
ms.assetid: 18fd4703-5939-491d-b759-985f767b951f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 응용 프로그램 마법사가 만든 레코드 뷰 코드  (MFC Data Access)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[MFC 응용 프로그램 마법사](../mfc/reference/database-support-mfc-application-wizard.md)는 뷰의 `OnInitialUpdate` 및 `OnGetRecordset` 멤버 함수를 재정의합니다.  프레임워크는 프레임 창, 문서 및 뷰를 만든 후 `OnInitialUpdate`를 호출하여 뷰를 초기화합니다.  `OnInitialUpdate`는 문서에서 레코드 집합에 대한 포인터를 가져옵니다.  기본 클래스 [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) 함수를 호출하면 레코드 집합이 열립니다.  다음 코드는 `CRecordView`에 대한 이 프로세스를 보여 줍니다. `CDaoRecordView`용 코드도 비슷합니다.  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
   m_pSet = &GetDocument()->m_sectionSet;  
   CRecordView::OnInitialUpdate();  
}  
```  
  
 레코드 집합이 열리면 레코드를 선택합니다.  [CRecordset::Open](../Topic/CRecordset::Open.md) 또는 [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md)는 첫 번째 레코드를 현재 레코드로 지정하고 DDX는 데이터를 레코드 집합의 필드 데이터 멤버에서 뷰의 해당 폼 컨트롤로 이동합니다.  RFX에 대한 자세한 내용은 [RFX\(레코드 필드 교환\)](../data/odbc/record-field-exchange-rfx.md)를 참조하세요.  DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.  문서\/뷰 작성 프로세스에 대한 자세한 내용은 [클래스를 사용하여 Windows 응용 프로그램 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)을 참조하세요.  
  
> [!NOTE]
>  최종 사용자가 레코드 집합에서의 레코드 뷰 컨트롤을 새로 고치는 기능을 제공해야 합니다.  이 기능을 제공하지 않는 경우 사용자가 컨트롤 값을 잘못된 값으로 변경하면 현재 레코드에서 영구적으로 작업이 중지될 수 있습니다.  컨트롤을 새로 고치려면 매개 변수 **FALSE**를 포함하여 `CWnd` 멤버 함수 [UpdateData](../Topic/CWnd::UpdateData.md)를 호출합니다.  
  
## 참고 항목  
 [레코드 뷰 사용](../data/using-a-record-view-mfc-data-access.md)