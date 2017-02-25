---
title: "CMFCPropertySheet Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertySheet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertySheet class"
  - "CMFCPropertySheet::OnInitDialog method"
  - "CMFCPropertySheet::PreTranslateMessage method"
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCPropertySheet Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCPropertySheet` 클래스는 각 속성 페이지가 페이지 탭, 도구 모음 단추, 트리 컨트롤 노드 또는 목록 항목으로 표시되는 속성 시트를 지원합니다.  
  
## 구문  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCPropertySheet::CMFCPropertySheet](../Topic/CMFCPropertySheet::CMFCPropertySheet.md)|`CMFCPropertySheet` 개체를 생성합니다.|  
|`CMFCPropertySheet::~CMFCPropertySheet`|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCPropertySheet::AddPage](../Topic/CMFCPropertySheet::AddPage.md)|속성 시트에 페이지를 추가합니다.|  
|[CMFCPropertySheet::AddPageToTree](../Topic/CMFCPropertySheet::AddPageToTree.md)|트리 컨트롤에 새 속성 페이지를 추가합니다.|  
|[CMFCPropertySheet::AddTreeCategory](../Topic/CMFCPropertySheet::AddTreeCategory.md)|트리 컨트롤에 새 노드를 추가합니다.|  
|[CMFCPropertySheet::EnablePageHeader](../Topic/CMFCPropertySheet::EnablePageHeader.md)|각 페이지 위쪽에서 사용자 지정 머리글을 그릴 공간을 예약합니다.|  
|[CMFCPropertySheet::GetHeaderHeight](../Topic/CMFCPropertySheet::GetHeaderHeight.md)|현재 머리글의 높이를 검색합니다.|  
|[CMFCPropertySheet::GetLook](../Topic/CMFCPropertySheet::GetLook.md)|현재 속성 시트의 모양을 지정하는 열거형 값을 검색합니다.|  
|[CMFCPropertySheet::GetNavBarWidth](../Topic/CMFCPropertySheet::GetNavBarWidth.md)|탐색 모음의 너비\(픽셀\)를 검색합니다.|  
|[CMFCPropertySheet::GetTab](../Topic/CMFCPropertySheet::GetTab.md)|현재 속성 시트 컨트롤을 지원하는 내부 탭 컨트롤 개체를 검색합니다.|  
|`CMFCPropertySheet::GetThisClass`|프레임워크에서 이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 가져오는 데 사용합니다.|  
|[CMFCPropertySheet::InitNavigationControl](../Topic/CMFCPropertySheet::InitNavigationControl.md)|현재 속성 시트 컨트롤의 모양을 초기화합니다.|  
|[CMFCPropertySheet::OnActivatePage](../Topic/CMFCPropertySheet::OnActivatePage.md)|속성 페이지를 사용하도록 설정한 경우 프레임워크에서 호출됩니다.|  
|[CMFCPropertySheet::OnDrawPageHeader](../Topic/CMFCPropertySheet::OnDrawPageHeader.md)|사용자 지정 속성 페이지 머리글을 그리기 위해 프레임워크에서 호출됩니다.|  
|`CMFCPropertySheet::OnInitDialog`|[WM\_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) 메시지를 처리합니다.  \([CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md) 재정의\)|  
|[CMFCPropertySheet::OnRemoveTreePage](../Topic/CMFCPropertySheet::OnRemoveTreePage.md)|트리 컨트롤에서 속성 페이지를 제거하기 위해 프레임워크에서 호출됩니다.|  
|`CMFCPropertySheet::PreTranslateMessage`|창 메시지가 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수로 디스패치되기 전에 변환합니다.  \(`CPropertySheet::PreTranslateMessage`를 재정의합니다.\)|  
|[CMFCPropertySheet::RemoveCategory](../Topic/CMFCPropertySheet::RemoveCategory.md)|트리 컨트롤에서 노드를 제거합니다.|  
|[CMFCPropertySheet::RemovePage](../Topic/CMFCPropertySheet::RemovePage.md)|속성 시트에서 속성 페이지를 제거합니다.|  
|[CMFCPropertySheet::SetIconsList](../Topic/CMFCPropertySheet::SetIconsList.md)|Outlook 창의 탐색 컨트롤에서 사용되는 이미지 목록을 지정합니다.|  
|[CMFCPropertySheet::SetLook](../Topic/CMFCPropertySheet::SetLook.md)|속성 시트의 모양을 지정합니다.|  
  
## 설명  
 `CMFCPropertySheet` 클래스는 속성 시트\(탭 대화 상자라고도 함\)를 나타냅니다.  `CMFCPropertySheet` 클래스는 다양한 방식으로 속성 페이지를 표시할 수 있습니다.  
  
 응용 프로그램에서 `CMFCPropertySheet` 클래스를 사용하려면 다음 단계를 수행합니다.  
  
1.  `CMFCPropertySheet` 클래스에서 클래스를 파생시키고 클래스 이름\(예: CMyPropertySheet\)을 지정합니다.  
  
2.  각 속성 페이지에 대해 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) 개체를 생성합니다.  
  
3.  CMyPropertySheet 생성자에서 [CMFCPropertySheet::SetLook](../Topic/CMFCPropertySheet::SetLook.md) 메서드를 호출합니다.  이 메서드의 매개 변수는 속성 페이지가 속성 시트의 위쪽이나 왼쪽에 있는 탭, Microsoft OneNote 속성 시트 스타일의 탭, Microsoft Outlook 도구 모음 컨트롤의 단추, 트리 컨트롤의 노드 또는 속성 시트의 왼쪽에 있는 항목 목록으로 표시되도록 지정합니다.  
  
4.  Microsoft Outlook 도구 모음 스타일로 속성 시트를 만드는 경우 [CMFCPropertySheet::SetIconsList](../Topic/CMFCPropertySheet::SetIconsList.md) 메서드를 호출하여 속성 페이지와 함께 이미지 목록을 연결합니다.  
  
5.  각 속성 페이지에 대해 [CMFCPropertySheet::AddPage](../Topic/CMFCPropertySheet::AddPage.md) 메서드를 호출합니다.  
  
6.  `CMFCPropertySheet` 컨트롤을 만들고 해당 `DoModal` 메서드를 호출합니다.  
  
## 그림  
 다음 그림에서는 포함된 Microsoft Outlook 도구 모음 스타일의 속성 시트를 보여 줍니다.  Outlook 도구 모음은 속성 시트의 왼쪽에 나타납니다.  
  
 ![CMFCPropertySheet 색 컨트롤](../../mfc/reference/media/cmfcpropertysheet_color.png "cmfcpropertysheet\_color")  
  
 다음 그림에서는 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md) 개체가 포함된 속성 시트를 보여 줍니다.  해당 개체는 표준 공용 컨트롤 속성 시트 스타일의 속성 시트입니다.  
  
 ![CMFCPropertySheet 목록 및 속성 컨트롤](../../mfc/reference/media/cmfcpropertysheet_list.png "cmfcpropertysheet\_list")  
  
 다음 그림에서는 트리 컨트롤 스타일의 속성 시트를 보여 줍니다.  
  
 ![속성 트리](../../mfc/reference/media/proptree.png "PropTree")  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
## 요구 사항  
 **헤더:** afxpropertysheet.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyPage Class](../../mfc/reference/cmfcpropertypage-class.md)   
 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)