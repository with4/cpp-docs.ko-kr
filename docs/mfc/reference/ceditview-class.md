---
title: "CEditView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEditView class"
  - "edit controls, 클래스"
  - "text editors"
  - "text editors, CEditView class"
  - "뷰, 클래스"
ms.assetid: bf38255c-fcbe-450c-95b2-3c5e35f86c37
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CEditView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows의 기능을 제공 하는 뷰 클래스의 형식 편집 컨트롤 및 간단한 텍스트 편집기 기능을 구현 하는 데 사용 합니다.  
  
## 구문  
  
```  
class CEditView : public CCtrlView  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CEditView::CEditView](../Topic/CEditView::CEditView.md)|개체 형식의 생성 `CEditView`.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CEditView::FindText](../Topic/CEditView::FindText.md)|텍스트 문자열을 검색 합니다.|  
|[CEditView::GetBufferLength](../Topic/CEditView::GetBufferLength.md)|문자 버퍼의 길이 가져옵니다.|  
|[CEditView::GetEditCtrl](../Topic/CEditView::GetEditCtrl.md)|액세스할 수 있는 `CEdit` 부분을 `CEditView` 개체 \(Windows 편집 컨트롤\).|  
|[CEditView::GetPrinterFont](../Topic/CEditView::GetPrinterFont.md)|현재 프린터 글꼴을 검색합니다.|  
|[CEditView::GetSelectedText](../Topic/CEditView::GetSelectedText.md)|현재 선택 된 텍스트를 검색합니다.|  
|[CEditView::LockBuffer](../Topic/CEditView::LockBuffer.md)|버퍼를 잠급니다.|  
|[CEditView::PrintInsideRect](../Topic/CEditView::PrintInsideRect.md)|지정 된 사각형 안에 텍스트를 렌더링합니다.|  
|[CEditView::SerializeRaw](../Topic/CEditView::SerializeRaw.md)|Serialize 된 `CEditView` 디스크 원시 텍스트 개체.|  
|[CEditView::SetPrinterFont](../Topic/CEditView::SetPrinterFont.md)|새 프린터 글꼴을 설정합니다.|  
|[CEditView::SetTabStops](../Topic/CEditView::SetTabStops.md)|설정 된 화면 표시와 인쇄에 대 한 탭.|  
|[CEditView::UnlockBuffer](../Topic/CEditView::UnlockBuffer.md)|버퍼의 잠금을 해제 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CEditView::OnFindNext](../Topic/CEditView::OnFindNext.md)|텍스트 문자열의 다음 항목을 찾습니다.|  
|[CEditView::OnReplaceAll](../Topic/CEditView::OnReplaceAll.md)|지정 된 문자열의 모든 항목을 새 문자열로 바꿉니다.|  
|[CEditView::OnReplaceSel](../Topic/CEditView::OnReplaceSel.md)|현재 선택 영역을 바꿉니다.|  
|[CEditView::OnTextNotFound](../Topic/CEditView::OnTextNotFound.md)|추가 텍스트에 맞게 찾기 작업이 실패 하면 호출 됩니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CEditView::dwStyleDefault](../Topic/CEditView::dwStyleDefault.md)|기본 개체 형식에 대 한 스타일  **CEditView.**|  
  
## 설명  
 `CEditView` 클래스는 다음과 같은 추가 기능을 제공 합니다.  
  
-   인쇄 합니다.  
  
-   찾기 및 바꾸기.  
  
 때문에 클래스 `CEditView` 에서 파생 된 클래스는 `CView`, 개체 클래스의 `CEditView` 문서와 문서 서식 파일로 사용할 수 있습니다.  
  
 각 `CEditView` 컨트롤의 텍스트 자체 전역 메모리 개체에 보관 됩니다.  응용 프로그램의 여러 가질 수 있습니다 `CEditView` 개체입니다.  
  
 만들 개체 형식의 `CEditView` 편집 창 위에 나열 된 추가 기능을 사용할 경우 또는 간단한 텍스트 편집기 기능을 원하는 경우.  A `CEditView` 개체 창의 전체 클라이언트 영역을 차지할 수 있습니다.  파생 클래스에서 `CEditView` 추가 또는 기본 기능을 수정 하거나 문서 서식 파일에 추가할 수 있는 클래스를 선언 합니다.  
  
 클래스의 기본 구현은 `CEditView` 다음 명령 처리:  **ID\_EDIT\_SELECT\_ALL**,  **ID\_EDIT\_FIND**,  **ID\_EDIT\_REPLACE**,  **ID\_EDIT\_REPEAT**, 및  **ID\_FILE\_PRINT**.  
  
 기본 문자 제한을 `CEditView` 입니다 \(1024 \* 1024\-1 \= 1048575\).  호출 하 여 변경 될 수 있는  **EM\_LIMITTEXT** 편집 컨트롤의 기본 기능.  그러나 한계는 운영 체제에 따라 다릅니다 및 유형을 편집 컨트롤 \(단일 또는 여러 줄\).  이러한 제한에 대 한 자세한 내용은  [EM\_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607).  
  
 컨트롤에서이 제한을 변경 하려면 재정의 `OnCreate()` 의 작동을 `CEditView` 클래스 및 코드의 다음 줄을 삽입:  
  
 [!code-cpp[NVC_MFCDocView#65](../../mfc/codesnippet/CPP/ceditview-class_1.cpp)]  
  
 개체 형식의 `CEditView` \(또는 파생 형식의 `CEditView`\)는 다음과 같은 제한이 있습니다:  
  
-   `CEditView`true를 구현 하지 않는 편집 \(WYSIWYG\) 가져올 확인할 수 있습니다.  일치 하는 인쇄 된 출력, 화면 가독성 사이의 선택 사항인 `CEditView` 화면 가독성을 선택할.  
  
-   `CEditView`텍스트는 단일 글꼴로 표시할 수 있습니다.  서식 없는 특수 문자는 지원 됩니다.  클래스를 참조 하십시오.  [CRichEditView](../../mfc/reference/cricheditview-class.md) 기능에 대 한.  
  
-   텍스트의 크기는 `CEditView` 포함할 수 제한 됩니다.  한계는 동일의 `CEdit` 제어 합니다.  
  
 에 대 한 자세한 내용은 `CEditView`를 참조 하십시오  [파생 뷰 클래스에서에서 사용할 수 있는 MFC](../../mfc/derived-view-classes-available-in-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CEditView`  
  
## 요구 사항  
 **헤더:** afxext.h  
  
## 참고 항목  
 [SUPERPAD MFC 샘플](../../top/visual-cpp-samples.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)