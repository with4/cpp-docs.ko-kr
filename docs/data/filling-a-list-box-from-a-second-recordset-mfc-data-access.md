---
title: " 번째 레코드 집합에서 목록 상자 채우기  (MFC Data Access) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComboBox 클래스, 둘째 행 집합에서 개체 채우기"
  - "CListCtrl 클래스, 둘째 레코드 집합에서 채우기"
  - "콤보 상자[C++], 둘째 레코드 집합에서 채우기"
  - "DAO 레코드 집합"
  - "DAO 레코드 집합, 목록 상자 또는 콤보 상자 채우기"
  - "목록 또는 콤보 상자 채우기"
  - "목록 상자, 둘째 레코드 집합에서 채우기"
  - "레코드 뷰의 다중 레코드 집합"
  - "ODBC 레코드 집합[C++], 목록 상자 또는 콤보 상자 채우기"
  - "레코드 뷰, 목록 상자 채우기"
  - "레코드 집합[C++], 목록 상자 또는 콤보 상자 채우기"
ms.assetid: 360c0834-da6b-4dc0-bcea-80e9acd611f0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
#  번째 레코드 집합에서 목록 상자 채우기  (MFC Data Access)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본적으로 레코드 뷰는 해당 필드가 레코드 뷰의 컨트롤로 매핑되는 단일 레코드 집합 개체와 연결됩니다.  레코드 뷰에 목록 상자 또는 콤보 상자 컨트롤을 삽입하고 두 번째 레코드 집합 개체의 값을 채우는 경우가 있습니다.  이때 사용자는 목록 상자를 사용하여 레코드 뷰에 표시할 새 정보 범주를 선택할 수 있습니다.  이 항목에서는 이러한 작업을 수행하는 방법과 시기에 대해 설명합니다.  
  
> [!TIP]
>  데이터 소스에서 콤보 상자나 목록 상자를 채우는 작업은 속도가 느릴 수 있습니다.  그러므로 가급적이면 레코드 수가 많은 레코드 집합에서 컨트롤을 채우지 않아야 합니다.  
  
 이 항목의 모델은 폼의 컨트롤을 채우는 기본 레코드 집합과 목록 상자 또는 콤보 상자를 채우는 두 번째 레코드 집합으로 구성됩니다.  목록 상자에서 문자열을 선택하면 선택한 항목에 따라 프로그램이 기본 레코드 집합을 다시 쿼리합니다.  다음 절차에서는 콤보 상자를 사용하지만 목록 상자에도 동일한 절차가 적용됩니다.  
  
#### 두 번째 레코드 집합에서 콤보 상자 또는 목록 상자를 채우려면  
  
1.  레코드 집합 개체\(ODBC의 경우 [CRecordset](../mfc/reference/crecordset-class.md), DAO의 경우 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)\)를 만듭니다.  
  
2.  콤보 상자 컨트롤의 [CComboBox](../mfc/reference/ccombobox-class.md) 개체에 대한 포인터를 가져옵니다.  
  
3.  콤보 상자에서 이전 콘텐츠를 비웁니다.  
  
4.  레코드 집합의 모든 레코드를 이동하면서 콤보 상자에 추가할 현재 레코드에서 각 문자열에 대해 [CComboBox::AddString](../Topic/CComboBox::AddString.md)을 호출합니다.  
  
5.  콤보 상자의 선택 항목을 초기화합니다.  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
    // ...  
  
    // Fill the combo box with all of the courses  
    CENROLLDoc* pDoc = GetDocument();  
    if (!pDoc->m_courseSet.Open())  
        return;  
  
    // ...  
  
    m_ctlCourseList.ResetContent();  
    if (pDoc->m_courseSet.IsOpen())  
    {   
        while (!pDoc->m_courseSet.IsEOF() )  
        {  
            m_ctlCourseList.AddString(  
                pDoc->m_courseSet.m_CourseID);  
            pDoc->m_courseSet.MoveNext();  
        }  
    }  
    m_ctlCourseList.SetCurSel(0);  
}  
```  
  
 이 함수는 제공되는 각 과정에 대한 레코드를 포함하는 두 번째 레코드 집합\(`m_courseSet`\)과 레코드 뷰 클래스에 저장되는 `CComboBox` 컨트롤\(`m_ctlCourseList`\)을 사용합니다.  
  
 함수는 문서에서 `m_courseSet`를 가져와서 엽니다.  그런 다음 `m_ctlCourseList`를 비우고 `m_courseSet`를 스크롤합니다.  그리고 각 레코드에 대해 콤보 상자의 `AddString` 멤버 함수를 호출하여 레코드의 과정 ID 값을 추가합니다.  마지막으로 코드가 콤보 상자의 선택 항목을 설정합니다.  
  
## 참고 항목  
 [레코드 뷰  \(MFC Data Access\)](../data/record-views-mfc-data-access.md)   
 [ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)