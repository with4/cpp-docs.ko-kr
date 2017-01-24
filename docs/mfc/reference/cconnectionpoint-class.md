---
title: "CConnectionPoint Class | Microsoft Docs"
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
  - "CConnectionPoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CConnectionPoint class"
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CConnectionPoint Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일종의 "연결 지점입니다." 라는 다른 OLE 개체와 통신 하는 데 사용 되는 인터페이스를 정의 합니다.  
  
## 구문  
  
```  
class CConnectionPoint : public CCmdTarget  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CConnectionPoint::CConnectionPoint](../Topic/CConnectionPoint::CConnectionPoint.md)|`CConnectionPoint` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CConnectionPoint::GetConnections](../Topic/CConnectionPoint::GetConnections.md)|연결 맵에 모든 연결 지점을 검색합니다.|  
|[CConnectionPoint::GetContainer](../Topic/CConnectionPoint::GetContainer.md)|연결 맵에 소유 하는 컨트롤의 컨테이너를 검색 합니다.|  
|[CConnectionPoint::GetIID](../Topic/CConnectionPoint::GetIID.md)|연결 지점의 인터페이스 ID를 검색합니다.|  
|[CConnectionPoint::GetMaxConnections](../Topic/CConnectionPoint::GetMaxConnections.md)|연결 지점 컨트롤에서 지 원하는 최대 수를 검색 합니다.|  
|[CConnectionPoint::GetNextConnection](../Topic/CConnectionPoint::GetNextConnection.md)|연결 요소에 대 한 포인터를 검색 합니다. `pos`.|  
|[CConnectionPoint::GetStartPosition](../Topic/CConnectionPoint::GetStartPosition.md)|반환 하 여 맵을 반복 시작는  **위치** 에 전달 된 값은 `GetNextConnection` 호출.|  
|[CConnectionPoint::OnAdvise](../Topic/CConnectionPoint::OnAdvise.md)|설정 하거나 연결을 끊는 경우 프레임 워크에서 호출 됩니다.|  
|[CConnectionPoint::QuerySinkInterface](../Topic/CConnectionPoint::QuerySinkInterface.md)|요청 된 싱크 인터페이스 포인터를 검색합니다.|  
  
## 설명  
 구현 및 OLE 컨트롤의 기능을 노출 하는 데 사용 되는, 일반 OLE 인터페이스와는 달리, 연결점 수 변경 알림 이벤트를 발생 시키는 다른 개체에 대 한 작업을 시작 하는 송신 인터페이스를 구현 합니다.  
  
 연결 된 두 부분으로 구성 됩니다: "원본" 및 인터페이스를 구현 하는 개체 인터페이스를 호출 하는 개체 "싱크" 라는 연결 지점을 제공 하 여 소스 싱크를 자체에 대 한 연결을 설정할 수 있습니다.  연결 지점 메커니즘을 통해 원본 개체가 싱크 구현 집합의 멤버 함수에 대 한 포인터를 가져옵니다.  예를 들어, 싱크에 의해 구현 된 이벤트를 발생 시키려면 소스 싱크 구현에 적절 한 메서드를 호출할 수 있습니다.  
  
 기본적으로 `COleControl`\-파생된 클래스 구현 두 연결점: 이벤트에 대 한 속성 변경 알림.  이러한 연결에 사용 되는, 각각 때 \(예를 들어, 컨트롤의 컨테이너\)는 싱크 알림 및 이벤트 발생에 대 한 속성 값이 변경 되었습니다.  지원 추가 연결 지점을 구현 하려면 OLE 컨트롤에 대 한 정보도 제공 됩니다.  컨트롤 클래스에 구현 된 각 추가 연결 지점에 대 한 "연결 지점을 구현 하는 연결 부분"을 선언 해야 합니다.  하나 이상의 연결 지점을 구현 하는 경우 단일 컨트롤 클래스에 "연결 맵"을 선언 해야 합니다.  
  
 단순한 연결 맵과 한 연결 지점에 대 한 다음 예제는 `Sample` OLE 컨트롤을 두 개의 코드 조각으로 구성 된: 첫 번째 부분을 연결 맵과 포인트 선언 두 번째가 맵과 연결 지점을 구현합니다.  첫 번째 단편에서 컨트롤 클래스의 선언에 꽂혀 있는 `protected` 섹션:  
  
 [!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/CPP/cconnectionpoint-class_1.h)]  
  
 `BEGIN_CONNECTION_PART` 및 `END_CONNECTION_PART` 매크로 포함 된 클래스를 선언 합니다. `XSampleConnPt` \(파생 `CConnectionPoint`\)은이 특정 연결 지점을 구현 합니다.  재정의 하려는 경우 `CConnectionPoint` 멤버 함수 또는 멤버 함수를 직접 추가,이 사이의 이러한 두 매크로 선언 합니다.  예를 들어,는 `CONNECTION_IID` 매크로 재정의 `CConnectionPoint::GetIID` 멤버 함수 사이의 이러한 두 매크로가 놓으면.  
  
 구현 파일에 두 번째 코드 조각 삽입 \(.CPP\) 컨트롤 클래스.  이 코드는 추가 연결 지점을 포함 하는 연결 맵 구현 `SampleConnPt`.  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/CPP/cconnectionpoint-class_2.cpp)]  
  
 이러한 코드 조각이 삽입 된 후 샘플 OLE 컨트롤의 연결 지점을 노출의  **ISampleSink** 인터페이스.  
  
 일반적으로 연결 지점은 "동일한 인터페이스에 연결 된 여러 개의 싱크를 방송 하는 것입니다 하는" 멀티 캐스팅, 지원 합니다.  다음 코드 단편은 각 연결 지점 싱크 반복 하 여 멀티 캐스팅을 수행 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/CPP/cconnectionpoint-class_3.cpp)]  
  
 연결의 현재 집합을 검색 하는이 예제는 `SampleConnPt` 연결 지점에 대 한 호출을 `CConnectionPoint::GetConnections`.  다음 연결 및 호출을 통해 반복 `ISampleSink::SinkFunc` 모든 활성 연결을 합니다.  
  
 사용에 대 한 자세한 내용은 `CConnectionPoint`, 문서를 참조 하십시오.  [연결점](../../mfc/connection-points.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## 요구 사항  
 **헤더:**  afxdisp.h  
  
## 참고 항목  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)