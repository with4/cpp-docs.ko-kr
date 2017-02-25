---
title: "CDynamicChain Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDynamicChain"
  - "ATL.CDynamicChain"
  - "CDynamicChain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicChain class"
  - "chaining message maps"
  - "message maps, 연결"
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDynamicChain Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스의 메시지 맵을 동적 체인을 지 원하는 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CDynamicChain  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDynamicChain::CDynamicChain](../Topic/CDynamicChain::CDynamicChain.md)|생성자입니다.|  
|[CDynamicChain::~CDynamicChain](../Topic/CDynamicChain::~CDynamicChain.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDynamicChain::CallChain](../Topic/CDynamicChain::CallChain.md)|다른 개체의 메시지 맵에 Windows 메시지를 보냅니다.|  
|[CDynamicChain::RemoveChainEntry](../Topic/CDynamicChain::RemoveChainEntry.md)|메시지 맵 항목 컬렉션에서 제거합니다.|  
|[CDynamicChain::SetChainEntry](../Topic/CDynamicChain::SetChainEntry.md)|메시지 맵 엔트리를 컬렉션에 추가 하거나 기존 항목을 수정 합니다.|  
  
## 설명  
 `CDynamicChain`컬렉션의 개체의 메시지 맵에 런타임에 전달 하는 Windows 메시지를 사용 하면 메시지 맵 관리 합니다.  
  
 동적 메시지 맵을의 체인에 대 한 지원을 추가 하려면 다음과 같이 하십시오.  
  
-   파생 클래스에서 `CDynamicChain`.  메시지 맵에 지정 된  [CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md) 연결할 개체의 기본 메시지 맵 매크로.  
  
-   연결 하려는 모든 클래스 파생  [CMessageMap](../../atl/reference/cmessagemap-class.md).  `CMessageMap`해당 메시지 맵을 다른 개체를 노출 하는 개체 수 있습니다.  
  
-   호출 `CDynamicChain::SetChainEntry` 개체와 메시지 맵을 체인으로 연결 하려는 식별 합니다.  
  
 예를 들어, 클래스는 다음과 같이 정의 되어 있다고 가정 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/CPP/cdynamicchain-class_1.h)]  
  
 그런 다음 클라이언트 호출 `CMyWindow::SetChainEntry`.  
  
 [!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/CPP/cdynamicchain-class_2.cpp)]  
  
 위치 `chainedObj` 체인으로 연결 된 개체 및 파생 된 클래스의 인스턴스인 `CMessageMap`.  이제 경우 `myCtl` 에서 처리 되지 않은 메시지가 `OnPaint` 또는 `OnSetFocus`, 창 프로시저에 보낼 `chainedObj`의 기본 메시지 맵.  
  
 메시지 맵 체인에 대 한 자세한 내용은 참조 하십시오.  [메시지 맵](../../atl/message-maps-atl.md) 의 문서 "ATL 창 클래스"  
  
## 요구 사항  
 **헤더:**  atlwin.h  
  
## 참고 항목  
 [CWindowImpl Class](../../atl/reference/cwindowimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)