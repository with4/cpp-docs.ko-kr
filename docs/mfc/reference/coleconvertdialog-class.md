---
title: "COleConvertDialog Class | Microsoft Docs"
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
  - "COleConvertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleConvertDialog class"
  - "변환 대화 상자"
  - "대화 상자, OLE"
  - "OLE Convert dialog box"
  - "OLE 대화 상자, Convert"
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleConvertDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

자세한 내용은  [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) 의 구조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 구문  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleConvertDialog::COleConvertDialog](../Topic/COleConvertDialog::COleConvertDialog.md)|`COleConvertDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleConvertDialog::DoConvert](../Topic/COleConvertDialog::DoConvert.md)|대화 상자에 지정 된 변환을 수행 합니다.|  
|[COleConvertDialog::DoModal](../Topic/COleConvertDialog::DoModal.md)|OLE 변경 항목 대화 상자를 표시합니다.|  
|[COleConvertDialog::GetClassID](../Topic/COleConvertDialog::GetClassID.md)|가져옵니다의  **CLSID** 선택한 항목에 연결 합니다.|  
|[COleConvertDialog::GetDrawAspect](../Topic/COleConvertDialog::GetDrawAspect.md)|아이콘으로 항목을 그릴 것인지 여부를 지정 합니다.|  
|[COleConvertDialog::GetIconicMetafile](../Topic/COleConvertDialog::GetIconicMetafile.md)|이 항목의 스크롤바 폼과 관련 된 메타 파일에 대 한 핸들을 가져옵니다.|  
|[COleConvertDialog::GetSelectionType](../Topic/COleConvertDialog::GetSelectionType.md)|선택 영역의 형식을 가져옵니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleConvertDialog::m\_cv](../Topic/COleConvertDialog::m_cv.md)|대화 상자의 동작을 제어 하는 구조입니다.|  
  
## 설명  
  
> [!NOTE]
>  응용 프로그램 마법사에서 생성 된 컨테이너 코드가이 클래스를 사용합니다.  
  
 특정 OLE 대화 상자에 대 한 자세한 내용은  [대화 상자에서 OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## 요구 사항  
 **헤더:**  afxodlgs.h  
  
## 참고 항목  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)