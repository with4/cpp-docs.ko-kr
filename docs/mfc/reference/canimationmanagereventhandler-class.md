---
title: CAnimationManagerEventHandler 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::OnManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationManagerEventHandler [MFC], CAnimationManagerEventHandler
- CAnimationManagerEventHandler [MFC], CreateInstance
- CAnimationManagerEventHandler [MFC], OnManagerStatusChanged
- CAnimationManagerEventHandler [MFC], SetAnimationController
ms.assetid: 6089ec07-e661-4805-b227-823b4652aade
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 62a775457d6da763a5c8426146d421a4cc958454
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955650"
---
# <a name="canimationmanagereventhandler-class"></a>CAnimationManagerEventHandler 클래스
애니메이션 관리자의 상태가 변경될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationManagerEventHandler::CAnimationManagerEventHandler](#canimationmanagereventhandler)|`CAnimationManagerEventHandler` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimationManagerEventHandler::CreateInstance](#createinstance)|인스턴스를 만들고 `CAnimationManagerEventHandler` 개체입니다.|  
|[CAnimationManagerEventHandler::OnManagerStatusChanged](#onmanagerstatuschanged)|애니메이션 관리자의 상태가 변경 될 때 호출 됩니다. (`CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`를 재정의합니다.)|  
|[CAnimationManagerEventHandler::SetAnimationController](#setanimationcontroller)|경로 이벤트에는 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.|  
  
## <a name="remarks"></a>설명  
 이 이벤트 처리기 만들고 CAnimationController::EnableAnimationManagerEvent를 호출 하는 경우 IUIAnimationManager::SetManagerEventHandler 메서드에 전달 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationManagerEventHandlerBase`  
  
 `CAnimationManagerEventHandler`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="canimationmanagereventhandler"></a>  CAnimationManagerEventHandler::CAnimationManagerEventHandler  
 [!INCLUDE[dev10_sp1required](../../mfc/reference/includes/dev10_sp1required_md.md)]  
  
 CAnimationManagerEventHandler 개체를 만듭니다.  
  
```  
CAnimationManagerEventHandler();
```  
  
##  <a name="createinstance"></a>  CAnimationManagerEventHandler::CreateInstance  
 [!INCLUDE[dev10_sp1required](../../mfc/reference/includes/dev10_sp1required_md.md)]  
  
 CAnimationManagerEventHandler 개체의 인스턴스를 만듭니다.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```  
  
### <a name="parameters"></a>매개 변수  
 *pAnimationController*  
 이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
 *ppManagerEventHandler*  
 출력입니다. 메서드가 성공 하는 경우 애니메이션 관리자에 대 한 상태 업데이트를 처리 하는 COM 개체에 대 한 포인터를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.  
  
##  <a name="onmanagerstatuschanged"></a>  CAnimationManagerEventHandler::OnManagerStatusChanged  
 [!INCLUDE[dev10_sp1required](../../mfc/reference/includes/dev10_sp1required_md.md)]  
  
 애니메이션 관리자의 상태가 변경 될 때 호출 됩니다.  
  
```  
IFACEMETHOD(OnManagerStatusChanged)(
  UI_ANIMATION_MANAGER_STATUS newStatus,
  UI_ANIMATION_MANAGER_STATUS previousStatus);
```  
  
### <a name="parameters"></a>매개 변수  
 *newStatus*  
 새 상태입니다.  
  
 *previousStatus*  
 이전 상태입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 구현에서는 항상; S_OK를 반환합니다.  
  
##  <a name="setanimationcontroller"></a>  CAnimationManagerEventHandler::SetAnimationController  
 [!INCLUDE[dev10_sp1required](../../mfc/reference/includes/dev10_sp1required_md.md)]  
  
 경로 이벤트에는 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>매개 변수  
 *pAnimationController*  
 이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
