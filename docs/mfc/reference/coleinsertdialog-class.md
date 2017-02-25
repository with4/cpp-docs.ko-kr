---
title: "COleInsertDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleInsertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleInsertDialog class"
  - "대화 상자, OLE"
  - "Insert Object dialog box"
  - "OLE Insert Object dialog box"
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleInsertDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

개체 삽입 대화 상자를 사용 합니다.  
  
## 구문  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleInsertDialog::COleInsertDialog](../Topic/COleInsertDialog::COleInsertDialog.md)|`COleInsertDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleInsertDialog::CreateItem](../Topic/COleInsertDialog::CreateItem.md)|대화 상자에서 선택한 항목을 만듭니다.|  
|[COleInsertDialog::DoModal](../Topic/COleInsertDialog::DoModal.md)|개체 삽입 대화 상자를 표시합니다.|  
|[COleInsertDialog::GetClassID](../Topic/COleInsertDialog::GetClassID.md)|가져옵니다의  **CLSID** 선택한 항목에 연결 합니다.|  
|[COleInsertDialog::GetDrawAspect](../Topic/COleInsertDialog::GetDrawAspect.md)|아이콘으로 항목을 그릴지 여부를 지정 합니다.|  
|[COleInsertDialog::GetIconicMetafile](../Topic/COleInsertDialog::GetIconicMetafile.md)|이 항목의 스크롤바 폼과 관련 된 메타 파일에 대 한 핸들을 가져옵니다.|  
|[COleInsertDialog::GetPathName](../Topic/COleInsertDialog::GetPathName.md)|대화 상자에서 선택한 파일의 전체 경로 가져옵니다.|  
|[COleInsertDialog::GetSelectionType](../Topic/COleInsertDialog::GetSelectionType.md)|선택한 개체의 형식을 가져옵니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleInsertDialog::m\_io](../Topic/COleInsertDialog::m_io.md)|구조체 형식의  **OLEUIINSERTOBJECT** 는 대화 상자의 동작을 제어 합니다.|  
  
## 설명  
 만들 개체의 클래스 `COleInsertDialog` 이 대화 상자를 호출 합니다.  후에 `COleInsertDialog` 개체를 생성 되었습니다, 사용할 수 있습니다는  [m\_io](../Topic/COleInsertDialog::m_io.md) 구조 값 또는 대화 상자에서 컨트롤의 상태를 초기화 합니다.  `m_io` 구조체의 형식이  **OLEUIINSERTOBJECT**.  이 대화 상자 클래스를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오의  [DoModal](../Topic/COleInsertDialog::DoModal.md) 멤버 함수입니다.  
  
> [!NOTE]
>  응용 프로그램 마법사에서 생성 된 컨테이너 코드가이 클래스를 사용합니다.  
  
 자세한 내용은  [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) 의 구조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 특정 OLE 대화 상자에 대 한 자세한 내용은  [대화 상자에서 OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## 요구 사항  
 **헤더:**  afxodlgs.h  
  
## 참고 항목  
 [MFC 샘플 OCLIENT](../../top/visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)