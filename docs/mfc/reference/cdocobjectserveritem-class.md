---
title: "CDocObjectServerItem Class | Microsoft Docs"
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
  - "CDocObjectServerItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "CDocObjectServerItem class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocObjectServerItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구현 OLE 서버 DocObject 서버에 특정 동사입니다.  
  
## 구문  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDocObjectServerItem::CDocObjectServerItem](../Topic/CDocObjectServerItem::CDocObjectServerItem.md)|`CDocObjectServerItem` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDocObjectServerItem::GetDocument](../Topic/CDocObjectServerItem::GetDocument.md)|항목이 들어 있는 문서에 대 한 포인터를 검색 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDocObjectServerItem::OnHide](../Topic/CDocObjectServerItem::OnHide.md)|프레임 워크는 DocObject 항목 숨기기 하려고 하면 예외가 throw 됩니다.|  
|[CDocObjectServerItem::OnShow](../Topic/CDocObjectServerItem::OnShow.md)|프레임 워크에서의 DocObject 항목 위치를 확인 하 라는 활성화 합니다.  호출 된 DocObject 항목인 경우  [COleServerItem::OnShow](../Topic/COleServerItem::OnShow.md).|  
  
## 설명  
 `CDocObjectServerItem`재정의 가능한 멤버 함수 정의:  [OnHide](../Topic/CDocObjectServerItem::OnHide.md),  [OnOpen](http://msdn.microsoft.com/ko-kr/7a9b1363-6ad8-4732-9959-4e35c07644fd), 및  [OnShow](../Topic/CDocObjectServerItem::OnShow.md).  
  
 사용 하 `CDocObjectServerItem`, 사용의  [OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md) 에서 재정의 `COleServerDoc`\-파생 된 클래스 반환 된 새 `CDocObjectServerItem` 개체.  항목의 모든 기능을 변경 하는 경우 새 인스턴스를 직접 만들 수 있습니다 `CDocObjectServerItem`\-클래스를 파생 합니다.  
  
 자세한 내용은 DocObjects 참조 하십시오.  [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) 및  [COleCmdUI](../../mfc/reference/colecmdui-class.md) 에 있는  *MFC 참조*.  참고  [인터넷 첫 번째 단계: 액티브 문서](../../mfc/active-documents-on-the-internet.md) 및  [활성 문서](../../mfc/active-documents-on-the-internet.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## 요구 사항  
 **헤더:**  afxdocob.h  
  
## 참고 항목  
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer Class](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem Class](../../mfc/reference/coledocobjectitem-class.md)