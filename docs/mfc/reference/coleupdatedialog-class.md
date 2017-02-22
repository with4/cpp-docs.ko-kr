---
title: "COleUpdateDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleUpdateDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleUpdateDialog class"
  - "링크[C++], 업데이트"
  - "OLE 대화 상자, Edit Link"
  - "OLE link updating"
  - "Update dialog"
  - "updating OLE links"
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleUpdateDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용에 대 한 특수 한 경우의 연결 편집 대화 상자를 사용 해야만 기존 업데이트 해야 연결 또는 문서에 포함 된 개체입니다.  
  
## 구문  
  
```  
class COleUpdateDialog : public COleLinksDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleUpdateDialog::COleUpdateDialog](../Topic/COleUpdateDialog::COleUpdateDialog.md)|`COleUpdateDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleUpdateDialog::DoModal](../Topic/COleUpdateDialog::DoModal.md)|표시는  **링크 편집** 는 업데이트 모드에서 대화 상자.|  
  
## 설명  
 특정 OLE 대화 상자에 대 한 자세한 내용은  [대화 상자에서 OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
 `COleUpdateDialog`  
  
## 요구 사항  
 **헤더:**  afxodlgs.h  
  
## 참고 항목  
 [MFC 샘플 OCLIENT](../../top/visual-cpp-samples.md)   
 [COleLinksDialog Class](../../mfc/reference/colelinksdialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleLinksDialog Class](../../mfc/reference/colelinksdialog-class.md)