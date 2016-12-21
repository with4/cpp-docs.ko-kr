---
title: "COleDialog Class | Microsoft Docs"
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
  - "COleDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDialog class"
  - "대화 상자, OLE"
  - "OLE 대화 상자, 기본 클래스"
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE에 대 한 대화 상자에 공통 기능을 제공합니다.  
  
## 구문  
  
```  
class COleDialog : public CCommonDialog  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleDialog::GetLastError](../Topic/COleDialog::GetLastError.md)|대화 상자에서 반환 된 오류 코드를 가져옵니다.|  
  
## 설명  
 여러 클래스에서 파생 된 Mfc 라이브러리를 제공 `COleDialog`.  
  
-   [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)  
  
-   [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)  
  
-   [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)  
  
-   [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
-   [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)  
  
-   [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)  
  
-   [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)  
  
-   [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)  
  
-   [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)  
  
 특정 OLE 대화 상자에 대 한 자세한 내용은  [대화 상자에서 OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `COleDialog`  
  
## 요구 사항  
 **헤더:**  afxodlgs.h  
  
## 참고 항목  
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)