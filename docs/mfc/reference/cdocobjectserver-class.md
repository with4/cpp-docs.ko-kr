---
title: "CDocObjectServer Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDocObjectServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "CDocObjectServer class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDocObjectServer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일반 확인 하는 데 필요한 추가 OLE 인터페이스 구현 `COleDocument` 전체 DocObject 서버에 서버: `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`, 및 `IPrint`.  
  
## 구문  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDocObjectServer::CDocObjectServer](../Topic/CDocObjectServer::CDocObjectServer.md)|`CDocObjectServer` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDocObjectServer::ActivateDocObject](../Topic/CDocObjectServer::ActivateDocObject.md)|문서 개체 서버가 활성화 되지만 표시 되지 않습니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDocObjectServer::OnActivateView](../Topic/CDocObjectServer::OnActivateView.md)|DocObject 뷰를 표시합니다.|  
|[CDocObjectServer::OnApplyViewState](../Topic/CDocObjectServer::OnApplyViewState.md)|DocObject 뷰의 상태를 복원합니다.|  
|[CDocObjectServer::OnSaveViewState](../Topic/CDocObjectServer::OnSaveViewState.md)|DocObject 뷰의 상태를 저장합니다.|  
  
## 설명  
 `CDocObjectServer`파생 된 `CCmdTarget` 와 밀접 하 게 협력 하 고 `COleServerDoc` 인터페이스를 노출 합니다.  
  
 DocObject 서버 문서를 포함할 수 있습니다  [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) 항목 DocObject 서버 인터페이스를 나타내는 개체입니다.  
  
 DocObject 서버를 사용자 지정 하려면이 클래스에서 파생 `CDocObjectServer` 보기 설정 기능을 무시 하 고  [OnActivateView](../Topic/CDocObjectServer::OnActivateView.md),  [OnApplyViewState](../Topic/CDocObjectServer::OnApplyViewState.md), 및  [OnSaveViewState](../Topic/CDocObjectServer::OnSaveViewState.md).  Framework 호출에 클래스의 새 인스턴스를 제공 해야 합니다.  
  
 자세한 내용은 DocObjects 참조 하십시오.  [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) 및  [COleCmdUI](../../mfc/reference/colecmdui-class.md) 에 있는  *MFC 참조*.  참고  [인터넷 첫 번째 단계: 액티브 문서](../../mfc/active-documents-on-the-internet.md) 및  [활성 문서](../../mfc/active-documents-on-the-internet.md).  
  
 또한 다음 기술 자료 문서를 참조 하십시오.  
  
-   : Q247382 PRB: ActiveX 문서 컨테이너에서 숨겨진 컨트롤 ActiveX 문서 서버에 대 한 도구 설명  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## 요구 사항  
 **헤더:**  afxdocob.h  
  
## 참고 항목  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem Class](../../mfc/reference/cdocobjectserveritem-class.md)