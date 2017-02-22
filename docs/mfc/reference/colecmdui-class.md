---
title: "COleCmdUI Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX documents [C++], document server"
  - "COleCmdUI class"
  - "docobject server"
  - "document object server"
  - "servers [C++], ActiveX documents"
  - "servers [C++], doc objects"
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleCmdUI Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구현 MFC 사용자 인터페이스 개체의 상태를 업데이트 하는 방법 관련 하 여 `IOleCommandTarget`\-응용 프로그램의 기능을 제어 합니다.  
  
## 구문  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleCmdUI::COleCmdUI](../Topic/COleCmdUI::COleCmdUI.md)|`COleCmdUI` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleCmdUI::Enable](../Topic/COleCmdUI::Enable.md)|설정 하거나 사용 명령 플래그를 지웁니다.|  
|[COleCmdUI::SetCheck](../Topic/COleCmdUI::SetCheck.md)|켜기\/끄기 켜기\/끄기 상태 설정 명령.|  
|[COleCmdUI::SetText](../Topic/COleCmdUI::SetText.md)|명령에 대 한 텍스트 이름 또는 상태 문자열을 반환합니다.|  
  
## 설명  
 사용자 프로세스 MFC 응용 프로그램에서 메뉴를 볼 때 Docobjects를 사용할 수 없는 응용 프로그램에서  **UPDATE\_COMMAND\_UI** notifcations.  각 알림 제공 되는  [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체는 특정 명령의 상태를 반영 하도록 조작할 수 있습니다.  그러나 MFC 응용 프로그램에 대 한 DocObjects 사용 하는 경우를 처리  **UPDATE\_OLE\_COMMAND\_UI** 알림 및 할당 `COleCmdUI` 개체입니다.  
  
 `COleCmdUI`해당 컨테이너의 사용자 인터페이스 \(예: FileNew, 열기, 인쇄 및 등\)에서 시작 명령을 수신할 수 있는 DocObject 고 컨테이너는 DocObject 사용자 인터페이스 명령을 받을 수 있습니다.  하지만 `IDispatch` 같은 명령에서 발송 하는 데 사용할 수 있습니다 `IOleCommandTarget` 쿼리 및 형식 정보가 포함 된 표준 집합을 일반적으로 인수 없이 명령 사용 하 고 있기 때문에 실행 하는 간단한 방법을 제공 합니다.  `COleCmdUI`설정, 업데이트 및 기타 DocObject 사용자 인터페이스 명령 속성을 설정 하려면 사용할 수 있습니다.  호출 명령을 호출 하는 경우  [COleServerDoc::OnExecOleCmd](../Topic/COleServerDoc::OnExecOleCmd.md).  
  
 자세한 내용은 DocObjects 참조 하십시오.  [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) 및  [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md).  참고  [인터넷 첫 번째 단계: 액티브 문서](../../mfc/active-documents-on-the-internet.md) 및  [활성 문서](../../mfc/active-documents-on-the-internet.md).  
  
## 상속 계층 구조  
 [CCmdUI](../../mfc/reference/ccmdui-class.md)  
  
 `COleCmdUI`  
  
## 요구 사항  
 **헤더:**  afxdocobj.h  
  
## 참고 항목  
 [CCmdUI Class](../../mfc/reference/ccmdui-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)