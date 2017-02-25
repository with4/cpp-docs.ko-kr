---
title: "CMFCRibbonUndoButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonUndoButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonUndoButton class"
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCRibbonUndoButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonUndoButton` 최신 사용자 명령을 포함 하는 드롭다운 목록 단추 클래스를 구현 합니다.  사용자가 가장 최근에 사용한 명령 중 하나를 취소 하거나 다시 실행 하려면 드롭다운 목록에서 선택할 수 있습니다.  
  
## 구문  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](../Topic/CMFCRibbonUndoButton::CMFCRibbonUndoButton.md)|새 구문 `CMFCRibbonUndoButton` 개체를 지정 하는 명령 ID, 텍스트 레이블 및 부모 개체의 이미지 목록에서 이미지를 사용 하 여.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonUndoButton::AddUndoAction](../Topic/CMFCRibbonUndoButton::AddUndoAction.md)|작업 목록에 새 작업을 추가합니다.|  
|[CMFCRibbonUndoButton::CleanUpUndoList](../Topic/CMFCRibbonUndoButton::CleanUpUndoList.md)|드롭다운 목록에서 작업 목록을 지웁니다.|  
|[CMFCRibbonUndoButton::GetActionNumber](../Topic/CMFCRibbonUndoButton::GetActionNumber.md)|사용자가 드롭다운 목록에서 선택한 항목의 수를 결정 합니다.|  
|[CMFCRibbonUndoButton::HasMenu](../Topic/CMFCRibbonUndoButton::HasMenu.md)|개체 메뉴에 포함 되어 있는지 여부를 나타냅니다.|  
  
## 설명  
 `CMFCRibbonUndoButton` 클래스 드롭다운 목록을 나타내는 데 스택을 사용 합니다.  
  
## 예제  
 다음 예제에서는 개체를 생성 하는 방법을 보여 줍니다.는 `CMFCRibbonUndoButton` 클래스 및 작업 목록에 새 동작을 추가 합니다.  이 코드 조각에 속하지는  [샘플 가젯을 리본](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RibbonGadgets#2](../../mfc/reference/codesnippet/CPP/cmfcribbonundobutton-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## 요구 사항  
 **헤더:** afxribbonundobutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery Class](../../mfc/reference/cmfcribbongallery-class.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)