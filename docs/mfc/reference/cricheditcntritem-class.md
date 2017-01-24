---
title: "CRichEditCntrItem Class | Microsoft Docs"
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
  - "CRichEditCntrItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCntrItem class"
  - "OLE items, in rich edit views"
  - "rich edit 컨트롤, OLE items"
  - "rich edit 컨트롤, using"
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRichEditCntrItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와  [CRichEditView](../../mfc/reference/cricheditview-class.md) 및  [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), MFC의 문서 뷰 아키텍처의 컨텍스트 내에서 풍부한 편집 컨트롤의 기능을 제공 합니다.  
  
## 구문  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CRichEditCntrItem::CRichEditCntrItem](../Topic/CRichEditCntrItem::CRichEditCntrItem.md)|`CRichEditCntrItem` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRichEditCntrItem::SyncToRichEditObject](../Topic/CRichEditCntrItem::SyncToRichEditObject.md)|다른 형식으로 항목을 활성화합니다.|  
  
## 설명  
 "Rich edit 컨트롤" 사용자를 입력 하 고 텍스트를 편집 하는 창입니다.  텍스트 문자 및 단락 서식을 지정할 수 있으며 포함 된 OLE 개체를 포함할 수 있습니다.  Rich edit 컨트롤 텍스트 서식에 대 한 프로그래밍 인터페이스를 제공 합니다.  그러나 응용 프로그램이 모든 사용자에 게 서식 지정 작업을 사용할 수 있도록 하는 데 필요한 사용자 인터페이스 구성 구현 해야 합니다.  
  
 `CRichEditView`텍스트와 텍스트의 서식 특성을 유지합니다.  `CRichEditDoc`보기에서 사용 하는 OLE 클라이언트 항목 목록을 유지 합니다.  `CRichEditCntrItem`OLE 클라이언트 항목 컨테이너 쪽 액세스를 제공합니다.  
  
 이 Windows 공용 컨트롤 \(즉는  [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 MFC 응용 프로그램에 rich edit 컨테이너 항목을 사용 하는 방법에 대 한 예제를 참조 하십시오의  [워드 패드](../../top/visual-cpp-samples.md) 샘플 응용 프로그램입니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [활성화](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## 요구 사항  
 **헤더:**  afxrich.h  
  
## 참고 항목  
 [MFC 샘플 워드 패드](../../top/visual-cpp-samples.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc Class](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)