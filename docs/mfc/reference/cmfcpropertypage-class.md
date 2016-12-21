---
title: "CMFCPropertyPage Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyPage class"
  - "CMFCPropertyPage::CreateObject method"
  - "CMFCPropertyPage::OnSetActive method"
  - "CMFCPropertyPage::PreTranslateMessage method"
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCPropertyPage` 클래스 속성 페이지에서 팝업 메뉴의 표시를 지원 합니다.  
  
## 구문  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCPropertyPage::CMFCPropertyPage](../Topic/CMFCPropertyPage::CMFCPropertyPage.md)|`CMFCPropertyPage` 개체를 생성합니다.|  
|`CMFCPropertyPage::~CMFCPropertyPage`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCPropertyPage::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|`CMFCPropertyPage::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|`CMFCPropertyPage::OnSetActive`|페이지는 사용자가 선택 하 고 활성 페이지가 됩니다 때이 멤버 함수는 프레임 워크에서 호출 됩니다.  \(재정의 [CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md).\)|  
|`CMFCPropertyPage::PreTranslateMessage`|창 메시지를 디스패치하기 전에 변환의  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 기능입니다.  자세한 내용과 메서드 구문 [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(재정의 `CPropertyPage::PreTranslateMessage`.\)|  
  
## 설명  
 `CMFCPropertyPage` 탭 대화 상자로 알려져 속성 시트의 개별 페이지를 나타내는 클래스입니다.  
  
 사용 된 `CMFCPropertyPage` 과 함께 클래스는  [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) 클래스.  속성 페이지에서 메뉴를 사용 하려면 모두 바꾸기를 `CPropertyPage` 클래스에 `CMFCPropertyPage` 클래스.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
## 요구 사항  
 **헤더:** afxpropertypage.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertySheet Class](../../mfc/reference/cmfcpropertysheet-class.md)