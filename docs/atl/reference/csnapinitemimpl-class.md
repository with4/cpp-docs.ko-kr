---
title: "CSnapInItemImpl Class | Microsoft Docs"
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
  - "CSnapInItemImpl"
  - "ATL.CSnapInItemImpl"
  - "ATL::CSnapInItemImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSnapInItemImpl class"
  - "snap-ins"
  - "snap-ins, ATL support for"
  - "snap-ins, data items"
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSnapInItemImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 스냅인 노드 개체를 구현 하는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class T,  
BOOL bIsExtension= FALSE  
>  
class ATL_NO_VTABLE CSnapInItemImpl :  
public CSnapInItem  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `CSnapInItemImpl`.  
  
 *bIsExtension*  
 **True 이면** 경우 개체는 스냅인 확장. 그렇지 않으면  **거짓**.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSnapInItemImpl::CSnapInItemImpl](../Topic/CSnapInItemImpl::CSnapInItemImpl.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSnapInItemImpl::AddMenuItems](../Topic/CSnapInItemImpl::AddMenuItems.md)|상황에 맞는 메뉴에 메뉴 항목을 추가합니다.|  
|[CSnapInItemImpl::Command](../Topic/CSnapInItemImpl::Command.md)|사용자 지정 메뉴 항목을 선택 하면 콘솔에 의해 호출 됩니다.|  
|[CSnapInItemImpl::CreatePropertyPages](../Topic/CSnapInItemImpl::CreatePropertyPages.md)|스냅인의 속성 시트에 페이지를 추가 합니다.|  
|[CSnapInItemImpl::FillData](../Topic/CSnapInItemImpl::FillData.md)|지정 된 스트림으로 복사본 정보 스냅인 개체입니다.|  
|[CSnapInItemImpl::GetResultPaneInfo](../Topic/CSnapInItemImpl::GetResultPaneInfo.md)|검색은  **RESULTDATAITEM** 구조를 스냅인.|  
|[CSnapInItemImpl::GetResultViewType](../Topic/CSnapInItemImpl::GetResultViewType.md)|결과 창에서 사용 되는 보기 유형을 결정 합니다.|  
|[CSnapInItemImpl::GetScopePaneInfo](../Topic/CSnapInItemImpl::GetScopePaneInfo.md)|검색 된  **SCOPEDATAITEM** 스냅인의 구조.|  
|[CSnapInItemImpl::Notify](../Topic/CSnapInItemImpl::Notify.md)|콘솔에서 스냅인의 사용자가 수행한 작업을 알리기 위해 호출 됩니다.|  
|[CSnapInItemImpl::QueryPagesFor](../Topic/CSnapInItemImpl::QueryPagesFor.md)|스냅인 노드 속성 페이지를 지원 하는지 확인 하기 위해 호출 됩니다.|  
|[CSnapInItemImpl::SetMenuInsertionFlags](../Topic/CSnapInItemImpl::SetMenuInsertionFlags.md)|스냅인 개체 삽입 메뉴 플래그를 수정합니다.|  
|[CSnapInItemImpl::SetToolbarButtonInfo](../Topic/CSnapInItemImpl::SetToolbarButtonInfo.md)|지정 된 도구 모음 단추 정보를 설정합니다.|  
|[CSnapInItemImpl::UpdateMenuState](../Topic/CSnapInItemImpl::UpdateMenuState.md)|상황에 맞는 메뉴 항목의 상태를 업데이트합니다.|  
|[CSnapInItemImpl::UpdateToolbarButton](../Topic/CSnapInItemImpl::UpdateToolbarButton.md)|지정 된 도구 모음 단추의 상태를 업데이트합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CSnapInItemImpl::m\_bstrDisplayName](../Topic/CSnapInItemImpl::m_bstrDisplayName.md)|스냅인 개체의 이름입니다.|  
|[CSnapInItemImpl::m\_resultDataItem](../Topic/CSnapInItemImpl::m_resultDataItem.md)|Windows  **RESULTDATAITEM** 구조를 사용 하는 `CSnapInItemImpl` 개체.|  
|[CSnapInItemImpl::m\_scopeDataItem](../Topic/CSnapInItemImpl::m_scopeDataItem.md)|Windows  **SCOPEDATAITEM** 구조를 사용 하는 `CSnapInItemImpl` 개체.|  
  
## 설명  
 `CSnapInItemImpl`도구 모음 및 메뉴 항목 추가 및 명령을 해당 처리기 함수에 스냅인 노드에 대 한 전달는 스냅인 노드 개체의 기본 구현을 제공 합니다.  이러한 몇 가지 다른 인터페이스를 통해 구현 기능과 형식에 매핑합니다.  기본 구현에서는 올바른 파생된 클래스의 인스턴스를 확인 하 고 다음 정확한 인스턴스에 메시지를 전달 하는 노드 개체 보낸 알림을 처리 합니다.  
  
## 상속 계층 구조  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## 요구 사항  
 **헤더:**  atlsnap.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)