---
title: "CPropExchange Class | Microsoft Docs"
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
  - "CPropExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨트롤[MFC], OLE"
  - "CPropExchange 클래스"
  - "OLE 컨트롤, 지속성"
ms.assetid: ed872180-e770-4942-892a-92139d501fab
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPropExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지 속성의 구현에 대 한 OLE 컨트롤을 지원합니다.  
  
## 구문  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPropExchange::ExchangeBlobProp](../Topic/CPropExchange::ExchangeBlobProp.md)|이진 대형 개체 \(BLOB\) 속성을 교환합니다.|  
|[CPropExchange::ExchangeFontProp](../Topic/CPropExchange::ExchangeFontProp.md)|글꼴 속성을 교환합니다.|  
|[CPropExchange::ExchangePersistentProp](../Topic/CPropExchange::ExchangePersistentProp.md)|컨트롤 사이의 파일 속성을 교환합니다.|  
|[CPropExchange::ExchangeProp](../Topic/CPropExchange::ExchangeProp.md)|모든 기본 제공 형식의 등록 정보를 교환합니다.|  
|[CPropExchange::ExchangeVersion](../Topic/CPropExchange::ExchangeVersion.md)|OLE 컨트롤의 버전 번호를 교환합니다.|  
|[CPropExchange::GetVersion](../Topic/CPropExchange::GetVersion.md)|OLE 컨트롤의 버전 번호를 검색합니다.|  
|[CPropExchange::IsAsynchronous](../Topic/CPropExchange::IsAsynchronous.md)|속성 교환 비동기적으로 수행 하는 경우를 결정 합니다.|  
|[CPropExchange::IsLoading](../Topic/CPropExchange::IsLoading.md)|속성 중 여부를 나타내는 컨트롤에 로드 또는 저장을 합니다.|  
  
## 설명  
 `CPropExchange`기본 클래스에 없는 것입니다.  
  
 컨텍스트 및 속성 exchange의 방향을 설정합니다.  
  
 지 속성 컨트롤의 상태 정보, 컨트롤 자체는 보통 사이의 속성을 일반적으로 표현 됩니다.  
  
 프레임 워크에서 파생 된 개체 생성 `CPropExchange` OLE 컨트롤의 속성을 로드할 수 있는지 통지 되 면 또는 저장된 하는 영구 저장소입니다.  
  
 프레임 워크에 대 한 포인터를 전달 `CPropExchange` 개체를 컨트롤에 `DoPropExchange` 함수입니다.  마법사를 사용 하 여 해당 컨트롤의 경우 컨트롤의 기초 파일을 만들 경우 `DoPropExchange` 함수 호출 `COleControl::DoPropExchange`.  스톡 속성은 컨트롤의 기본 클래스 버전을 교환. 파생된 클래스의 버전 컨트롤에 추가한 exchange 속성을 수정 합니다.  
  
 `CPropExchange`컨트롤의 속성을 serialize 하거나 초기화할 로드 하거나 컨트롤을 만드는 시 컨트롤의 속성에 사용할 수 있습니다.  `ExchangeProp` 및 `ExchangeFontProp` 멤버 함수를 `CPropExchange` 속성에 저장 하 고 다른 미디어에서 로드할 수 있습니다.  
  
 사용에 대 한 자세한 내용은 `CPropExchange`, 문서를 참조 하십시오.  [ActiveX MFC 컨트롤: 속성 페이지](../../mfc/mfc-activex-controls-property-pages.md).  
  
## 상속 계층 구조  
 `CPropExchange`  
  
## 요구 사항  
 **헤더:**  afxctl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md)