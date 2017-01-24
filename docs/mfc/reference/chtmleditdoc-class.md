---
title: "CHtmlEditDoc Class | Microsoft Docs"
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
  - "CHtmlEditDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditDoc class"
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlEditDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와  [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), MFC 문서 뷰 아키텍처의 컨텍스트 내에서 WebBrowser 편집 플랫폼의 기능을 제공 합니다.  
  
## 구문  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHtmlEditDoc::CHtmlEditDoc](../Topic/CHtmlEditDoc::CHtmlEditDoc.md)|`CHtmlEditDoc` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHtmlEditDoc::GetView](../Topic/CHtmlEditDoc::GetView.md)|검색은 `CHtmlEditView` 개체는이 문서에 첨부 합니다.|  
|[CHtmlEditDoc::IsModified](../Topic/CHtmlEditDoc::IsModified.md)|WebBrowser 컨트롤에 연결 된 뷰는 사용자에 의해 수정 된 문서 포함 되어 있는지 여부를 반환 합니다.|  
|[CHtmlEditDoc::OpenURL](../Topic/CHtmlEditDoc::OpenURL.md)|URL을 엽니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `CHtmlEditDoc`  
  
## 요구 사항  
 **헤더:** afxhtml.h  
  
## 참고 항목  
 [HTMLEdit 샘플](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)