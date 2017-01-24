---
title: "COleTemplateServer Class | Microsoft Docs"
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
  - "COleTemplateServer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automation servers [C++], 구현"
  - "COleTemplateServer class"
  - "link containers [C++]"
  - "OLE link containers"
  - "OLE 서버 응용 프로그램, COleTemplateServer class"
  - "OLE 서버 응용 프로그램, managing server documents"
  - "서버, OLE"
  - "visual editing, 서버"
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleTemplateServer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 비주얼 편집 컨테이너 링크 \(지원 링크를 포함 하는 응용\), 자동화 서버 및 서버를 사용 합니다.  
  
## 구문  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleTemplateServer::COleTemplateServer](../Topic/COleTemplateServer::COleTemplateServer.md)|`COleTemplateServer` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleTemplateServer::ConnectTemplate](../Topic/COleTemplateServer::ConnectTemplate.md)|문서 서식 파일은 기본 연결 `COleObjectFactory` 개체입니다.|  
|[COleTemplateServer::Unregister](../Topic/COleTemplateServer::Unregister.md)|연결 된 문서 서식 파일의 등록을 취소 합니다.|  
|[COleTemplateServer::UpdateRegistry](../Topic/COleTemplateServer::UpdateRegistry.md)|문서 형식을 OLE 시스템 레지스트리에 등록합니다.|  
  
## 설명  
 이 클래스는 클래스에서 파생 된  [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md). 일반적으로 사용할 수 있습니다 `COleTemplateServer` 직접 대신 사용자 지정 클래스를 파생 합니다.  `COleTemplateServer`사용 하는  [만드](../../mfc/reference/cdoctemplate-class.md) 는 서버 문서를 관리 하는 개체입니다.  사용 `COleTemplateServer` 하 여 전체 서버, 독립 실행형 응용 프로그램으로 실행할 수 있는 서버를 구현 하는 경우.  단일 문서 인터페이스 \(SDI\) 응용 프로그램 지원 되지만 전체 서버는 일반적으로 다중 문서 인터페이스 \(MDI\) 응용 프로그램입니다.  한 `COleTemplateServer` 개체는 각 문서 형식에 응용 프로그램을 지원 합니다; 서버에 대 한 필요 워크시트와 차트 서버 응용 프로그램을 지 원하는 경우, 두 개 해야 `COleTemplateServer` 개체입니다.  
  
 `COleTemplateServer`재정의 `OnCreateInstance` 에 의해 정의 된 멤버 함수 `COleObjectFactory`.  이 멤버 함수는 적절 한 형식의 C\+\+ 개체를 만드는 프레임 워크에서 호출 됩니다.  
  
 서버에 대 한 자세한 내용은  [서버: 서버 구현](../../mfc/servers-implementing-a-server.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## 요구 사항  
 **헤더:**  afxdisp.h  
  
## 참고 항목  
 [HIERSVR MFC 샘플](../../top/visual-cpp-samples.md)   
 [COleObjectFactory Class](../../mfc/reference/coleobjectfactory-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)