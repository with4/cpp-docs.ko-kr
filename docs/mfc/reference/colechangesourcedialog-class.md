---
title: "COleChangeSourceDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleChangeSourceDialog"
  - "OLEUICHANGESOURCE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleChangeSourceDialog class"
  - "대화 상자, OLE"
  - "OLE Change Source dialog box"
  - "OLE 대화 상자, Change Source"
  - "OleUIChangeSource structure"
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleChangeSourceDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 원본 변경 대화 상자를 사용 합니다.  
  
## 구문  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](../Topic/COleChangeSourceDialog::COleChangeSourceDialog.md)|`COleChangeSourceDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleChangeSourceDialog::DoModal](../Topic/COleChangeSourceDialog::DoModal.md)|OLE 원본 변경 대화 상자를 표시합니다.|  
|[COleChangeSourceDialog::GetDisplayName](../Topic/COleChangeSourceDialog::GetDisplayName.md)|전체 소스 표시 이름을 가져옵니다.|  
|[COleChangeSourceDialog::GetFileName](../Topic/COleChangeSourceDialog::GetFileName.md)|파일 이름은 원본 이름에서 가져옵니다.|  
|[COleChangeSourceDialog::GetFromPrefix](../Topic/COleChangeSourceDialog::GetFromPrefix.md)|접두사를의 이전 소스를 가져옵니다.|  
|[COleChangeSourceDialog::GetItemName](../Topic/COleChangeSourceDialog::GetItemName.md)|항목 이름을 소스 이름을에서 가져옵니다.|  
|[COleChangeSourceDialog::GetToPrefix](../Topic/COleChangeSourceDialog::GetToPrefix.md)|접두사를는 새 소스를 가져옵니다.|  
|[COleChangeSourceDialog::IsValidSource](../Topic/COleChangeSourceDialog::IsValidSource.md)|원본이 유효한 지 여부를 나타냅니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleChangeSourceDialog::m\_cs](../Topic/COleChangeSourceDialog::m_cs.md)|대화 상자의 동작을 제어 하는 구조입니다.|  
  
## 설명  
 만들 개체의 클래스 `COleChangeSourceDialog` 이 대화 상자를 호출 합니다.  후에 `COleChangeSourceDialog` 개체를 생성 되었습니다, 사용할 수 있습니다는  [m\_cs](../Topic/COleChangeSourceDialog::m_cs.md) 구조 값 또는 대화 상자에서 컨트롤의 상태를 초기화 합니다.  `m_cs` 구조체의 형식이  [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160).  이 대화 상자 클래스를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오의  [DoModal](../Topic/COleChangeSourceDialog::DoModal.md) 멤버 함수입니다.  
  
 자세한 내용은  [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 특정 OLE 대화 상자에 대 한 자세한 내용은  [대화 상자에서 OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## 요구 사항  
 **헤더:**  afxodlgs.h  
  
## 참고 항목  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)