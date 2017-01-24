---
title: "CAnimationController 클래스 | Microsoft Docs"
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
  - "CAnimationController"
  - "afxanimationcontroller/CAnimationController"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationController 클래스"
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationController 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

애니메이션을 만들고 관리하기 위한 중앙 인터페이스를 제공하는 애니메이션 컨트롤러를 구현합니다.  
  
## 구문  
  
```  
class CAnimationController : public CObject;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationController::CAnimationController](../Topic/CAnimationController::CAnimationController.md)|애니메이션 컨트롤러를 생성합니다.|  
|[CAnimationController::~CAnimationController](../Topic/CAnimationController::~CAnimationController.md)|소멸자  애니메이션 컨트롤러 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationController::AddAnimationObject](../Topic/CAnimationController::AddAnimationObject.md)|애니메이션 컨트롤러에 속하는 그룹에 애니메이션 개체를 추가합니다.|  
|[CAnimationController::AddKeyframeToGroup](../Topic/CAnimationController::AddKeyframeToGroup.md)|키프레임을 그룹에 추가합니다.|  
|[CAnimationController::AnimateGroup](../Topic/CAnimationController::AnimateGroup.md)|애니메이션을 실행할 그룹을 준비하고 필요에 따라 일정을 세웁니다.|  
|[CAnimationController::CleanUpGroup](../Topic/CAnimationController::CleanUpGroup.md)|오버로드.  애니메이션을 예약할 때 그룹을 정리하기 위해 프레임워크에 의해 호출됩니다.|  
|[CAnimationController::CreateKeyframe](../Topic/CAnimationController::CreateKeyframe.md)|오버로드.  전환에 따라 달라지는 키프레임을 만들고 지정된 그룹에 추가합니다.|  
|[CAnimationController::EnableAnimationManagerEvent](../Topic/CAnimationController::EnableAnimationManagerEvent.md)|애니메이션 관리자의 상태가 변경될 때 호출할 처리기를 설정하거나 해제합니다.|  
|[CAnimationController::EnableAnimationTimerEventHandler](../Topic/CAnimationController::EnableAnimationTimerEventHandler.md)|타이밍 이벤트 처리기 및 타이밍 업데이트 처리기를 설정하거나 해제합니다.|  
|[CAnimationController::EnablePriorityComparisonHandler](../Topic/CAnimationController::EnablePriorityComparisonHandler.md)|예약된 스토리보드를 취소, 완료, 잘라내기 또는 압축할 수 있는지 여부를 확인하려면 우선 순위 비교 처리기를 설정하거나 해제합니다.|  
|[CAnimationController::EnableStoryboardEventHandler](../Topic/CAnimationController::EnableStoryboardEventHandler.md)|스토리보드 상태 및 업데이트 이벤트에 대한 처리기를 설정하거나 해제합니다.|  
|[CAnimationController::FindAnimationGroup](../Topic/CAnimationController::FindAnimationGroup.md)|오버로드.  스토리보드를 사용하여 애니메이션 그룹을 찾습니다.|  
|[CAnimationController::FindAnimationObject](../Topic/CAnimationController::FindAnimationObject.md)|지정된 애니메이션 변수를 포함하고 있는 애니메이션 개체를 찾습니다.|  
|[CAnimationController::GetKeyframeStoryboardStart](../Topic/CAnimationController::GetKeyframeStoryboardStart.md)|스토리보드 시작을 나타내는 키프레임을 반환합니다.|  
|[CAnimationController::GetUIAnimationManager](../Topic/CAnimationController::GetUIAnimationManager.md)|캡슐화된 IUIAnimationManager 개체에 대한 액세스를 제공합니다.|  
|[CAnimationController::GetUIAnimationTimer](../Topic/CAnimationController::GetUIAnimationTimer.md)|캡슐화된 IUIAnimationTimer 개체에 대한 액세스를 제공합니다.|  
|[CAnimationController::GetUITransitionFactory](../Topic/CAnimationController::GetUITransitionFactory.md)|IUIAnimationTransitionFactory 인터페이스에 대한 포인터 또는 전환 라이브러리를 만들지 못한 경우 NULL입니다.|  
|[CAnimationController::GetUITransitionLibrary](../Topic/CAnimationController::GetUITransitionLibrary.md)|캡슐화된 IUIAnimationTransitionLibrary 개체에 대한 액세스를 제공합니다.|  
|[CAnimationController::IsAnimationInProgress](../Topic/CAnimationController::IsAnimationInProgress.md)|하나 이상의 그룹이 애니메이션을 재생하는지 여부를 지정합니다.|  
|[CAnimationController::IsValid](../Topic/CAnimationController::IsValid.md)|애니메이션 컨트롤러가 유효한지 여부를 지정합니다.|  
|[CAnimationController::OnAnimationIntegerValueChanged](../Topic/CAnimationController::OnAnimationIntegerValueChanged.md)|애니메이션 변수의 정수 값이 변경되었을 때 프레임워크에 의해 호출됩니다.|  
|[CAnimationController::OnAnimationManagerStatusChanged](../Topic/CAnimationController::OnAnimationManagerStatusChanged.md)|애니메이션 관리자에서 StatusChanged 이벤트에 대한 응답으로 프레임워크에 의해 호출됩니다.|  
|[CAnimationController::OnAnimationTimerPostUpdate](../Topic/CAnimationController::OnAnimationTimerPostUpdate.md)|애니메이션 업데이트가 완료된 후에 프레임워크에 의해 호출됩니다.|  
|[CAnimationController::OnAnimationTimerPreUpdate](../Topic/CAnimationController::OnAnimationTimerPreUpdate.md)|애니메이션 업데이트를 시작하기 전에 프레임워크에 의해 호출됩니다.|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](../Topic/CAnimationController::OnAnimationTimerRenderingTooSlow.md)|애니메이션에 대한 렌더링 프레임 속도가 원하는 최소 프레임 속도 이하일 때 프레임워크에 의해 호출되었습니다.|  
|[CAnimationController::OnAnimationValueChanged](../Topic/CAnimationController::OnAnimationValueChanged.md)|애니메이션 변수의 값이 변경되었을 때 프레임워크에 의해 호출됩니다.|  
|[CAnimationController::OnBeforeAnimationStart](../Topic/CAnimationController::OnBeforeAnimationStart.md)|애니메이션을 예약하기 바로 전에 프레임워크에 의해 호출됩니다.|  
|[CAnimationController::OnHasPriorityCancel](../Topic/CAnimationController::OnHasPriorityCancel.md)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출되었습니다.|  
|[CAnimationController::OnHasPriorityCompress](../Topic/CAnimationController::OnHasPriorityCompress.md)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출되었습니다.|  
|[CAnimationController::OnHasPriorityConclude](../Topic/CAnimationController::OnHasPriorityConclude.md)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출되었습니다.|  
|[CAnimationController::OnHasPriorityTrim](../Topic/CAnimationController::OnHasPriorityTrim.md)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출되었습니다.|  
|[CAnimationController::OnStoryboardStatusChanged](../Topic/CAnimationController::OnStoryboardStatusChanged.md)|스토리보드 상태가 변경되었을 때 프레임워크에 의해 호출됩니다.|  
|[CAnimationController::OnStoryboardUpdated](../Topic/CAnimationController::OnStoryboardUpdated.md)|스토리보드가 업데이트되었을 때 프레임워크에 의해 호출됩니다.|  
|[CAnimationController::RemoveAllAnimationGroups](../Topic/CAnimationController::RemoveAllAnimationGroups.md)|애니메이션 컨트롤러에서 애니메이션 그룹을 모두 제거합니다.|  
|[CAnimationController::RemoveAnimationGroup](../Topic/CAnimationController::RemoveAnimationGroup.md)|애니메이션 컨트롤러에서 지정된 ID를 가진 애니메이션 그룹을 제거합니다.|  
|[CAnimationController::RemoveAnimationObject](../Topic/CAnimationController::RemoveAnimationObject.md)|애니메이션 컨트롤러에서 애니메이션 개체를 제거합니다.|  
|[CAnimationController::RemoveTransitions](../Topic/CAnimationController::RemoveTransitions.md)|지정된 그룹에 속하는 애니메이션 개체에서 전환을 제거합니다.|  
|[CAnimationController::ScheduleGroup](../Topic/CAnimationController::ScheduleGroup.md)|애니메이션을 예약합니다.|  
|[CAnimationController::SetRelatedWnd](../Topic/CAnimationController::SetRelatedWnd.md)|애니메이션 컨트롤러와 창 간에 관계를 설정합니다.|  
|[CAnimationController::UpdateAnimationManager](../Topic/CAnimationController::UpdateAnimationManager.md)|애니메이션 관리자가 모든 애니메이션 변수의 값을 업데이트하도록 지시합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationController::CleanUpGroup](../Topic/CAnimationController::CleanUpGroup.md)|오버로드.  그룹을 정리하는 도우미입니다.|  
|[CAnimationController::OnAfterSchedule](../Topic/CAnimationController::OnAfterSchedule.md)|지정된 그룹에 대한 애니메이션을 예약했을 때 프레임워크에 의해 호출됩니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationController::g\_KeyframeStoryboardStart](../Topic/CAnimationController::g_KeyframeStoryboardStart.md)|스토리보드 시작을 나타내는 키프레임입니다.|  
|[CAnimationController::m\_bIsValid](../Topic/CAnimationController::m_bIsValid.md)|애니메이션 컨트롤러가 유효한지 여부를 지정합니다.  이 멤버는 현재 운영 체제가 Windows 애니메이션 API를 지원하지 않는 경우 FALSE로 설정됩니다.|  
|[CAnimationController::m\_lstAnimationGroups](../Topic/CAnimationController::m_lstAnimationGroups.md)|이 애니메이션 컨트롤러가 속한 애니메이션 그룹 목록입니다.|  
|[CAnimationController::m\_pAnimationManager](../Topic/CAnimationController::m_pAnimationManager.md)|애니메이션 관리자 COM 개체에 대한 포인터를 저장합니다.|  
|[CAnimationController::m\_pAnimationTimer](../Topic/CAnimationController::m_pAnimationTimer.md)|애니메이션 타이머 COM 개체에 대한 포인터를 저장합니다.|  
|[CAnimationController::m\_pRelatedWnd](../Topic/CAnimationController::m_pRelatedWnd.md)|애니메이션 관리자의 상태가 변경되거나 사후 업데이트 이벤트가 발생한 경우 자동으로 다시 그려질 수 있는 관련된 CWnd 개체에 대한 포인터입니다.  NULL일 수 있습니다.|  
|[CAnimationController::m\_pTransitionFactory](../Topic/CAnimationController::m_pTransitionFactory.md)|전환 팩토리 COM 개체에 대한 포인터를 저장합니다.|  
|[CAnimationController::m\_pTransitionLibrary](../Topic/CAnimationController::m_pTransitionLibrary.md)|전환 라이브러리 COM 개체에 대한 포인터를 저장합니다.|  
  
## 설명  
 CAnimationController 클래스는 애니메이션을 관리하는 핵심 클래스입니다.  응용 프로그램에서 애니메이션 컨트롤러의 인스턴스를 하나 이상 만들고 선택적으로 CAnimationController::SetRelatedWnd를 사용하여 애니메이션 컨트롤러의 인스턴스를 CWnd 개체에 연결할 수 있습니다.  이 연결은 애니메이션 관리자 상태가 변경되었거나 애니메이션 타이머가 업데이트되었을 때 WM\_PAINT 메시지를 관련 창으로 자동으로 보내는 데 필요합니다.  이 관계를 활성화하지 않는 경우 수동으로 애니메이션을 표시하는 창을 다시 그려야 합니다.  이런 목적을 위해 CAnimationController에서 클래스를 파생시키고 OnAnimationManagerStatusChanged 및\/또는 OnAnimationTimerPostUpdate를 재정의하고 필요하면 하나 이상의 창을 무효화할 수 있습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationController](../../mfc/reference/canimationcontroller-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)