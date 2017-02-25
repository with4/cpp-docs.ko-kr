---
title: "CDocItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDocItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocItem class"
  - "client document items"
  - "container document items"
  - "document items"
  - "items, 문서"
  - "OLE 문서, items"
  - "server documents"
  - "server documents, document items"
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CDocItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구성 요소는 문서 데이터는 문서 항목에 대 한 기본 클래스입니다.  
  
## 구문  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDocItem::GetDocument](../Topic/CDocItem::GetDocument.md)|항목이 포함 된 문서를 반환 합니다.|  
|[CDocItem::IsBlank](../Topic/CDocItem::IsBlank.md)|항목에서 모든 정보가 들어 있는지 여부를 결정 합니다.|  
  
## 설명  
 `CDocItem`개체는 문서를 클라이언트와 서버 모두에서 OLE 항목을 나타내는 데 사용 됩니다.  
  
 자세한 내용은  [컨테이너: 컨테이너 구현](../../mfc/containers-implementing-a-container.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)