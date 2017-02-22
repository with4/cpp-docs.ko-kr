---
title: "COlePasteSpecialDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COlePasteSpecialDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePasteSpecialDialog class"
  - "대화 상자, Paste Special"
  - "OLE Paste Special dialog box"
  - "Paste Special dialog box"
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COlePasteSpecialDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 붙여넣기 특수 대화 상자를 사용 합니다.  
  
## 구문  
  
```  
  
class COlePasteSpecialDialog : public COleDialog  
  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](../Topic/COlePasteSpecialDialog::COlePasteSpecialDialog.md)|`COlePasteSpecialDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COlePasteSpecialDialog::AddFormat](../Topic/COlePasteSpecialDialog::AddFormat.md)|사용자 지정 형식을 응용 프로그램에 붙여 넣을 수 있는 형식 목록에 추가 합니다.|  
|[COlePasteSpecialDialog::AddLinkEntry](../Topic/COlePasteSpecialDialog::AddLinkEntry.md)|지원 되는 클립보드 형식 목록에 새 항목을 추가합니다.|  
|[COlePasteSpecialDialog::AddStandardFormats](../Topic/COlePasteSpecialDialog::AddStandardFormats.md)|추가  **CF\_BITMAP**,  **CF\_DIB**, `CF_METAFILEPICT`, 선택적으로 `CF_LINKSOURCE` 형식 목록에 응용 프로그램에 붙여넣을 수 있습니다.|  
|[COlePasteSpecialDialog::CreateItem](../Topic/COlePasteSpecialDialog::CreateItem.md)|지정 된 형식을 사용 하 여 컨테이너 문서에 항목을 만듭니다.|  
|[COlePasteSpecialDialog::DoModal](../Topic/COlePasteSpecialDialog::DoModal.md)|OLE 붙여넣기 특수 대화 상자를 표시합니다.|  
|[COlePasteSpecialDialog::GetDrawAspect](../Topic/COlePasteSpecialDialog::GetDrawAspect.md)|또는 항목 아이콘으로 그릴지 여부를 지정 합니다.|  
|[COlePasteSpecialDialog::GetIconicMetafile](../Topic/COlePasteSpecialDialog::GetIconicMetafile.md)|이 항목의 스크롤바 폼과 관련 된 메타 파일에 대 한 핸들을 가져옵니다.|  
|[COlePasteSpecialDialog::GetPasteIndex](../Topic/COlePasteSpecialDialog::GetPasteIndex.md)|사용자가 선택한 인덱스를 사용할 수 있는 붙여넣기 옵션을 가져옵니다.|  
|[COlePasteSpecialDialog::GetSelectionType](../Topic/COlePasteSpecialDialog::GetSelectionType.md)|선택 영역의 형식을 가져옵니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COlePasteSpecialDialog::m\_ps](../Topic/COlePasteSpecialDialog::m_ps.md)|구조체 형식의  **OLEUIPASTESPECIAL** 함수는 대화 상자 컨트롤입니다.|  
  
## 설명  
 만들 개체의 클래스 `COlePasteSpecialDialog` 이 대화 상자를 호출 합니다.  후는 `COlePasteSpecialDialog` 개체를 생성 되었습니다, 사용할 수 있는  [AddFormat](../Topic/COlePasteSpecialDialog::AddFormat.md) 및  [AddStandardFormats](../Topic/COlePasteSpecialDialog::AddStandardFormats.md) 클립보드 형식 대화 상자에 추가 하는 멤버 함수.  또한 사용할 수 있습니다는  [m\_ps](../Topic/COlePasteSpecialDialog::m_ps.md) 값 또는 대화 상자에서 컨트롤의 상태를 초기화 하는 구조.  `m_ps` 구조체의 형식이  **OLEUIPASTESPECIAL**.  
  
 자세한 내용은  [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) 의 구조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 특정 OLE 대화 상자에 대 한 자세한 내용은  [대화 상자에서 OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## 요구 사항  
 **헤더:**  afxodlgs.h  
  
## 참고 항목  
 [MFC 샘플 OCLIENT](../../top/visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)