---
title: "COlePropertiesDialog Class | Microsoft Docs"
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
  - "COlePropertiesDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePropertiesDialog class"
  - "대화 상자, OLE"
  - "Object Properties dialog box"
  - "OLE 문서, 속성 수정"
  - "OLE Object Properties dialog box"
  - "속성 페이지, OLE"
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COlePropertiesDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 일반 OLE 개체 속성 대화 상자를 캡슐화합니다.  
  
## 구문  
  
```  
  
class COlePropertiesDialog : public COleDialog  
  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COlePropertiesDialog::COlePropertiesDialog](../Topic/COlePropertiesDialog::COlePropertiesDialog.md)|`COlePropertiesDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COlePropertiesDialog::DoModal](../Topic/COlePropertiesDialog::DoModal.md)|대화 상자를 표시 하 고 선택할 수 있습니다.|  
|[COlePropertiesDialog::OnApplyScale](../Topic/COlePropertiesDialog::OnApplyScale.md)|문서 항목의 배율을 변경 하면 프레임 워크에서 호출 됩니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COlePropertiesDialog::m\_gp](../Topic/COlePropertiesDialog::m_gp.md)|"일반" 페이지를 초기화 하는 데 사용 되는 구조체는 `COlePropertiesDialog` 개체입니다.|  
|[COlePropertiesDialog::m\_lp](../Topic/COlePropertiesDialog::m_lp.md)|"링크" 페이지를 초기화 하는 데 사용 되는 구조체는 `COlePropertiesDialog` 개체입니다.|  
|[COlePropertiesDialog::m\_op](../Topic/COlePropertiesDialog::m_op.md)|구조체를 초기화 하는 데 사용 되는 `COlePropertiesDialog` 개체입니다.|  
|[COlePropertiesDialog::m\_psh](../Topic/COlePropertiesDialog::m_psh.md)|추가 사용자 지정 속성 페이지를 추가 하는 데 사용 되는 구조입니다.|  
|[COlePropertiesDialog::m\_vp](../Topic/COlePropertiesDialog::m_vp.md)|"보기" 페이지의 사용자 지정 하는 데 사용 되는 구조체는 `COlePropertiesDialog` 개체입니다.|  
  
## 설명  
 일반 OLE 개체 속성 대화 상자 표시 및 Windows 표준에 맞는 방식으로 OLE 문서 항목의 속성을 수정 하려면 손쉽게.  이러한 속성을 정보를 옵션 \(항목에 연결 된 경우\) 항목의 링크를 표시 하는 아이콘 및 이미지 배율 및 정보에 대 한 문서 항목을 나타내는 파일에 있습니다.  
  
 사용 하는 `COlePropertiesDialog` 개체, 먼저 사용 하 여 개체를 만들는 `COlePropertiesDialog` 생성자입니다.  대화 상자 생성 된 후 호출 하는 `DoModal` 멤버 함수를 대화 상자를 표시 하 고 항목의 모든 속성을 수정할 수 있습니다.  `DoModal`사용자가 확인 선택 여부를 반환 \(**IDOK**\) 또는 취소 \(**IDCANCEL**\) 단추.  확인 및 취소 단추 외에 적용 단추.  적용을 선택할 때 문서 항목의 등록 정보에 변경 내용을 항목에 적용 되 고 해당 이미지가 자동으로 업데이트 되지만 활성 상태로 유지 됩니다.  
  
 [M\_psh](../Topic/COlePropertiesDialog::m_psh.md) 데이터 멤버에 대 한 포인터입니다를  **PROPSHEETHEADER** 구조 및 않습니다 해야 명시적으로 액세스 하는 대부분의 경우에서.  추가 속성 페이지 기본 일반, 보기, 링크 페이지를 초과 해야 하는 경우는 예외가입니다.  수정할 수 있는 경우에 `m_psh` 데이터 멤버를 호출 하기 전에 사용자 지정 페이지를 포함 하는 `DoModal` 멤버 함수.  
  
 OLE 대화 상자에 대 한 자세한 내용은  [대화 상자에서 OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePropertiesDialog`  
  
## 요구 사항  
 **헤더:**  afxodlgs.h  
  
## 참고 항목  
 [CIRC MFC 샘플](../../top/visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [CPropertyPage Class](../../mfc/reference/cpropertypage-class.md)