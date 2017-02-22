---
title: "CCmdTarget Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCmdTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCmdTarget class"
  - "명령 라우팅, command targets"
  - "command targets"
  - "message maps, CCmdTarget base class"
  - "대상, 명령"
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CCmdTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mfc 라이브러리 메시지 맵 아키텍처에 대 한 기본 클래스입니다.  
  
## 구문  
  
```  
class CCmdTarget : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CCmdTarget::CCmdTarget](../Topic/CCmdTarget::CCmdTarget.md)|`CCmdTarget` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md)|커서를 모래 시계 커서 표시 됩니다.|  
|[CCmdTarget::DoOleVerb](../Topic/CCmdTarget::DoOleVerb.md)|OLE 동사가 수행 하는 지정 된 동작이 발생 합니다.|  
|[CCmdTarget::EnableAutomation](../Topic/CCmdTarget::EnableAutomation.md)|OLE 자동화에 대 한 수의 `CCmdTarget` 개체입니다.|  
|[CCmdTarget::EnableConnections](../Topic/CCmdTarget::EnableConnections.md)|연결 지점을 통해 이벤트 발생을 있습니다.|  
|[CCmdTarget::EnableTypeLib](../Topic/CCmdTarget::EnableTypeLib.md)|개체의 형식 라이브러리를 있습니다.|  
|[CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md)|이전 커서를 반환 합니다.|  
|[CCmdTarget::EnumOleVerbs](../Topic/CCmdTarget::EnumOleVerbs.md)|OLE 동사는 개체를 열거합니다.|  
|[CCmdTarget::FromIDispatch](../Topic/CCmdTarget::FromIDispatch.md)|반환에 대 한 포인터는 `CCmdTarget` 관련 개체의 `IDispatch` 포인터.|  
|[CCmdTarget::GetDispatchIID](../Topic/CCmdTarget::GetDispatchIID.md)|기본 디스패치 인터페이스 ID를 가져옵니다.|  
|[CCmdTarget::GetIDispatch](../Topic/CCmdTarget::GetIDispatch.md)|반환에 대 한 포인터는 `IDispatch` 관련 개체의 `CCmdTarget` 개체.|  
|[CCmdTarget::GetTypeInfoCount](../Topic/CCmdTarget::GetTypeInfoCount.md)|개체에서 제공 하는 형식 정보 인터페이스의 수를 검색 합니다.|  
|[CCmdTarget::GetTypeInfoOfGuid](../Topic/CCmdTarget::GetTypeInfoOfGuid.md)|지정된 GUID에 해당하는 형식 설명을 검색합니다.|  
|[CCmdTarget::GetTypeLib](../Topic/CCmdTarget::GetTypeLib.md)|포인터를 형식 라이브러리를 가져옵니다.|  
|[CCmdTarget::GetTypeLibCache](../Topic/CCmdTarget::GetTypeLibCache.md)|형식 라이브러리 캐시를 가져옵니다.|  
|[CCmdTarget::IsInvokeAllowed](../Topic/CCmdTarget::IsInvokeAllowed.md)|자동화 메서드를 호출할을 수 있습니다.|  
|[CCmdTarget::IsResultExpected](../Topic/CCmdTarget::IsResultExpected.md)|반환 된 자동화 기능을 사용할 경우 0이 아닌 값을 반환 해야 합니다.|  
|[CCmdTarget::OnCmdMsg](../Topic/CCmdTarget::OnCmdMsg.md)|경로 및 명령 메시지를 디스패치합니다.|  
|[CCmdTarget::OnFinalRelease](../Topic/CCmdTarget::OnFinalRelease.md)|마지막 OLE 참조가 해제 된 후 정리 합니다.|  
|[CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md)|모래 시계 커서를 복원합니다.|  
  
## 설명  
 메시지 맵을 작성 하 여 처리 하는 멤버 함수에 명령이 나 메시지를 라우팅합니다.  \(명령 메시지를 메뉴 항목, 명령 단추 또는 액셀러레이터 키입니다.\)  
  
 키 프레임 워크 클래스에서 파생 `CCmdTarget` 포함  [CView](../../mfc/reference/cview-class.md),  [CWinApp](../../mfc/reference/cwinapp-class.md),  [CDocument](../../mfc/reference/cdocument-class.md),  [CWnd](../../mfc/reference/cwnd-class.md), 및  [CFrameWnd](../../mfc/reference/cframewnd-class.md).  새 클래스에 대 한 메시지를 처리 하려면 다음 중 하나에서 클래스 파생 `CCmdTarget`\-클래스를 파생 합니다.  거의에서 클래스를 파생 시킬 `CCmdTarget` 직접.  
  
 개요를 명령 대상 및 `OnCmdMsg` 라우팅을 참조 하십시오.  [명령 대상](../../mfc/command-targets.md),  [명령 라우팅을](../../mfc/command-routing.md), 및  [메시지 매핑](../../mfc/mapping-messages.md).  
  
 `CCmdTarget`모래 시계 커서 표시를 처리 하는 멤버 함수를 포함 합니다.  원하는 명령을 실행 하는 눈에 띄는 시간 간격을 때 모래 시계 커서를 표시 합니다.  
  
 디스패치 맵 메시지 맵에 유사한, OLE 자동화를 제공 하는 `IDispatch` 기능.  이 인터페이스를 노출 하 여 다른 응용 프로그램 \(예: Visual Basic\)에 응용 프로그램을 호출할 수 있습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCmdTarget`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [ACDUAL MFC 샘플](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdUI Class](../../mfc/reference/ccmdui-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [COleDispatchDriver Class](../../mfc/reference/coledispatchdriver-class.md)