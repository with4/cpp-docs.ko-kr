---
title: "COleChangeIconDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleChangeIconDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Change Icon dialog box"
  - "COleChangeIconDialog class"
  - "대화 상자, OLE"
  - "OLE Change Icon dialog box"
  - "OLE 대화 상자, Change Icon"
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleChangeIconDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 아이콘 변경 대화 상자를 사용 합니다.  
  
## 구문  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleChangeIconDialog::COleChangeIconDialog](../Topic/COleChangeIconDialog::COleChangeIconDialog.md)|`COleChangeIconDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleChangeIconDialog::DoChangeIcon](../Topic/COleChangeIconDialog::DoChangeIcon.md)|지정 대화 상자에서 변경을 수행 합니다.|  
|[COleChangeIconDialog::DoModal](../Topic/COleChangeIconDialog::DoModal.md)|OLE 2 아이콘 변경 대화 상자를 표시합니다.|  
|[COleChangeIconDialog::GetIconicMetafile](../Topic/COleChangeIconDialog::GetIconicMetafile.md)|이 항목의 스크롤바 폼과 관련 된 메타 파일에 대 한 핸들을 가져옵니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleChangeIconDialog::m\_ci](../Topic/COleChangeIconDialog::m_ci.md)|대화 상자의 동작을 제어 하는 구조입니다.|  
  
## 설명  
 만들 개체의 클래스 `COleChangeIconDialog` 이 대화 상자를 호출 합니다.  후에 `COleChangeIconDialog` 개체를 생성 되었습니다, 사용할 수 있습니다는  [m\_ci](../Topic/COleChangeIconDialog::m_ci.md) 구조 값 또는 대화 상자에서 컨트롤의 상태를 초기화 합니다.  `m_ci` 구조체의 형식이  **OLEUICHANGEICON**.  이 대화 상자 클래스를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오의  [DoModal](../Topic/COleChangeIconDialog::DoModal.md) 멤버 함수입니다.  
  
 자세한 내용은  [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) 의 구조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 특정 OLE 대화 상자에 대 한 자세한 내용은  [대화 상자에서 OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## 요구 사항  
 **헤더:**  afxodlgs.h  
  
## 참고 항목  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)