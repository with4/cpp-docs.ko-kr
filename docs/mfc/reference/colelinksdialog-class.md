---
title: "COleLinksDialog Class | Microsoft Docs"
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
  - "COleLinksDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleLinksDialog class"
  - "대화 상자, OLE"
  - "Edit Links dialog box"
  - "OLE Edit Links dialog box"
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleLinksDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

연결 편집 대화 상자를 사용 합니다.  
  
## 구문  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleLinksDialog::COleLinksDialog](../Topic/COleLinksDialog::COleLinksDialog.md)|`COleLinksDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleLinksDialog::DoModal](../Topic/COleLinksDialog::DoModal.md)|연결 편집 대화 상자를 표시합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleLinksDialog::m\_el](../Topic/COleLinksDialog::m_el.md)|구조체 형식의  **OLEUIEDITLINKS** 는 대화 상자의 동작을 제어 합니다.|  
  
## 설명  
 만들 개체의 클래스 `COleLinksDialog` 이 대화 상자를 호출 합니다.  후에 `COleLinksDialog` 개체를 생성 되었습니다, 사용할 수 있습니다는  [m\_el](../Topic/COleLinksDialog::m_el.md) 구조 값 또는 대화 상자에서 컨트롤의 상태를 초기화 합니다.  `m_el` 구조체의 형식이  **OLEUIEDITLINKS**.  이 대화 상자 클래스를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오의  [DoModal](../Topic/COleLinksDialog::DoModal.md) 멤버 함수입니다.  
  
> [!NOTE]
>  응용 프로그램 마법사에서 생성 된 컨테이너 코드가이 클래스를 사용합니다.  
  
 자세한 내용은  [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) 의 구조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 특정 OLE 대화 상자에 대 한 자세한 내용은  [대화 상자에서 OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## 요구 사항  
 **헤더:**  afxodlgs.h  
  
## 참고 항목  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)