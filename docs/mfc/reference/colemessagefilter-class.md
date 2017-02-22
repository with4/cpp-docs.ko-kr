---
title: "COleMessageFilter Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleMessageFilter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램[OLE], managing interactions"
  - "COleMessageFilter class"
  - "message filters [C++]"
  - "메시지[C++], OLE"
  - "OLE[C++], managing concurrency"
  - "OLE 응용 프로그램[C++], managing interactions"
  - "OLE messages"
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleMessageFilter Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 응용 프로그램의 상호 작용에 의해 필요한 동시성을 관리 합니다.  
  
## 구문  
  
```  
class COleMessageFilter : public CCmdTarget  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleMessageFilter::COleMessageFilter](../Topic/COleMessageFilter::COleMessageFilter.md)|`COleMessageFilter` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleMessageFilter::BeginBusyState](../Topic/COleMessageFilter::BeginBusyState.md)|응용 프로그램을에서 사용 중 상태를 넣습니다.|  
|[COleMessageFilter::EnableBusyDialog](../Topic/COleMessageFilter::EnableBusyDialog.md)|수 있고, 호출된 응용 프로그램을 사용 중인 경우 표시 되는 대화 상자를 사용 하지 않습니다.|  
|[COleMessageFilter::EnableNotRespondingDialog](../Topic/COleMessageFilter::EnableNotRespondingDialog.md)|수 있으며 호출된 하는 응용 프로그램 응답 하지 않을 경우 표시 되는 대화 상자를 사용 하지 않습니다.|  
|[COleMessageFilter::EndBusyState](../Topic/COleMessageFilter::EndBusyState.md)|사용 중인 응용 프로그램의 상태를 종료합니다.|  
|[COleMessageFilter::OnMessagePending](../Topic/COleMessageFilter::OnMessagePending.md)|OLE 호출이 진행 중일 때 메시지를 처리 하는 프레임 워크에서 호출 합니다.|  
|[COleMessageFilter::Register](../Topic/COleMessageFilter::Register.md)|메시지 필터는 OLE 시스템 Dll을 등록합니다.|  
|[COleMessageFilter::Revoke](../Topic/COleMessageFilter::Revoke.md)|OLE 시스템 Dll 메시지 필터의 등록을 취소합니다.|  
|[COleMessageFilter::SetBusyReply](../Topic/COleMessageFilter::SetBusyReply.md)|OLE 호출이 사용 중인 응용 프로그램의 회신을 결정합니다.|  
|[COleMessageFilter::SetMessagePendingDelay](../Topic/COleMessageFilter::SetMessagePendingDelay.md)|응용 프로그램에 OLE 호출이 응답을 대기 하는 시간을 결정 합니다.|  
|[COleMessageFilter::SetRetryReply](../Topic/COleMessageFilter::SetRetryReply.md)|호출 응용 프로그램의 회신에는 실행 중인 응용 프로그램을 결정합니다.|  
  
## 설명  
 `COleMessageFilter` 클래스는 비주얼 편집 서버와 컨테이너 응용 프로그램, 뿐만 아니라 OLE 자동화 응용 프로그램에 유용 합니다.  호출 되는 서버 응용 프로그램에 대 한이 클래스 다른 컨테이너 응용 프로그램에서 들어오는 호출을 취소 하거나 나중에 다시 시도 되도록 응용 프로그램을 "사용" 하 사용할 수 있습니다.  이 클래스 호출 응용 프로그램에서 호출된 하는 응용 프로그램 사용량이 때 수행할 작업을 결정 하려면 사용할 수도 있습니다.  
  
 일반적인 용도 호출 하는 서버 응용 프로그램에 대 한  [BeginBusyState](../Topic/COleMessageFilter::BeginBusyState.md) 및  [EndBusyState](../Topic/COleMessageFilter::EndBusyState.md) 때이 수 문서 또는 소멸 될 다른 OLE 액세스 가능 개체에 대 한 위험 합니다.  이러한 호출에서  [CWinApp::OnIdle](../Topic/CWinApp::OnIdle.md) 동안 사용자 인터페이스를 업데이트 합니다.  
  
 기본적으로 `COleMessageFilter` 개체는 응용 프로그램이 초기화 될 때 할당 됩니다.  검색할 수 있는  [AfxOleGetMessageFilter](../Topic/AfxOleGetMessageFilter.md).  
  
 이 고급 클래스입니다. 거의 직접 작업을 해야 합니다.  
  
 자세한 내용은  [서버: 서버 구현](../../mfc/servers-implementing-a-server.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleMessageFilter`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)