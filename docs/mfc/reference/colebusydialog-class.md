---
title: "COleBusyDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleBusyDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleBusyDialog class"
  - "Server Busy dialog box"
  - "Server Not Responding dialog box"
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleBusyDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 서버가 응답 하지 또는 서버 작업 중 대화 상자를 사용 합니다.  
  
## 구문  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleBusyDialog::COleBusyDialog](../Topic/COleBusyDialog::COleBusyDialog.md)|`COleBusyDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleBusyDialog::DoModal](../Topic/COleBusyDialog::DoModal.md)|OLE 서버 작업 중 대화 상자가 표시 됩니다.|  
|[COleBusyDialog::GetSelectionType](../Topic/COleBusyDialog::GetSelectionType.md)|대화 상자에서 선택한을 결정 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleBusyDialog::m\_bz](../Topic/COleBusyDialog::m_bz.md)|구조체 형식의  **OLEUIBUSY** 는 대화 상자의 동작을 제어 합니다.|  
  
## 설명  
 만들 개체의 클래스 `COleBusyDialog` 이러한 대화 상자를 호출 합니다.  후에 `COleBusyDialog` 개체를 생성 되었습니다, 사용할 수 있습니다는  [m\_bz](../Topic/COleBusyDialog::m_bz.md) 구조 값 또는 대화 상자에서 컨트롤의 상태를 초기화 합니다.  `m_bz` 구조체의 형식이  **OLEUIBUSY**.  이 대화 상자 클래스를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오의  [DoModal](../Topic/COleBusyDialog::DoModal.md) 멤버 함수입니다.  
  
> [!NOTE]
>  응용 프로그램 마법사에서 생성 된 컨테이너 코드가이 클래스를 사용합니다.  
  
 자세한 내용은  [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) 의 구조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 특정 OLE 대화 상자에 대 한 자세한 내용은  [대화 상자에서 OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## 요구 사항  
 **헤더:**  afxodlgs.h  
  
## 참고 항목  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)