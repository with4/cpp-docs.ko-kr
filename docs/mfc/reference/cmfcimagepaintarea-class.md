---
title: "CMFCImagePaintArea Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCImagePaintArea"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCImagePaintArea class"
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMFCImagePaintArea Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이미지는 이미지 편집기 대화 상자에서 수정 하는 데 사용할 그림 영역을 제공 합니다.  
  
## 구문  
  
```  
class CMFCImagePaintArea : public CButton  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCImagePaintArea::CMFCImagePaintArea](../Topic/CMFCImagePaintArea::CMFCImagePaintArea.md)|`CMFCImagePaintArea` 개체를 생성합니다.|  
|`CMFCImagePaintArea::~CMFCImagePaintArea`|소멸자.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCImagePaintArea::GetMode](../Topic/CMFCImagePaintArea::GetMode.md)|현재 그리기 모드를 검색합니다.|  
|[CMFCImagePaintArea::SetBitmap](../Topic/CMFCImagePaintArea::SetBitmap.md)|그림 영역에 대 한 비트맵 이미지를 설정합니다.|  
|[CMFCImagePaintArea::SetColor](../Topic/CMFCImagePaintArea::SetColor.md)|현재 드로잉 색상을 설정합니다.|  
|[CMFCImagePaintArea::SetMode](../Topic/CMFCImagePaintArea::SetMode.md)|현재 그리기 모드를 설정합니다.|  
  
### 설명  
 이 클래스는 사용자 코드에서 직접 사용할 수 없습니다.  
  
 프레임 워크는이 클래스를 사용 하 여 그림 영역에는 이미지 편집기 대화 상자에 표시 합니다.  이미지 편집기 대화 상자에 대 한 자세한 내용은 [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## 예제  
 다음 예제에서는 개체를 생성 하는 방법을 보여 줍니다.는 `CMFCImagePaintArea` 클래스, 색상 드로잉을 현재 그리기 모드를 설정 하 고 그림 영역에 대 한 비트맵 이미지를 설정 합니다. 현재 설정 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/CPP/cmfcimagepaintarea-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)  
  
## 요구 사항  
 **헤더:** afximagepaintarea.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md)