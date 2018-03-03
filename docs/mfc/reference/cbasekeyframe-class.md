---
title: "CBaseKeyFrame 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
dev_langs:
- C++
helpviewer_keywords:
- CBaseKeyFrame [MFC], CBaseKeyFrame
- CBaseKeyFrame [MFC], AddToStoryboard
- CBaseKeyFrame [MFC], GetAnimationKeyframe
- CBaseKeyFrame [MFC], IsAdded
- CBaseKeyFrame [MFC], IsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_bAdded
- CBaseKeyFrame [MFC], m_bIsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_keyframe
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dba8ba22325d3ea9e68411f0372cfac4d6b0659d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame 클래스
키프레임의 기본 기능을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CBaseKeyFrame : public CObject;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|키 프레임 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|스토리 보드에 키 프레임을 추가 합니다.|  
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|기본 키 프레임 값을 반환합니다.|  
|[CBaseKeyFrame::IsAdded](#isadded)|키 프레임 스토리 보드에 추가 되었는지 여부를 지정 합니다.|  
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|키 프레임 오프셋에서 또는 전환 후 스토리 보드에 추가할지 여부를 지정 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[CBaseKeyFrame::m_bAdded](#m_badded)|이 키 프레임에 스토리 보드에 추가 되었는지 여부를 지정 합니다.|  
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|이 키 프레임에서 다른 기존 키 프레임의 오프셋 또는 일부 전환의 끝에서 스토리 보드에 추가할지 여부를 지정 합니다.|  
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Windows 애니메이션 API 키 프레임을 나타냅니다. 키 프레임 초기화 되지 않은 UI_ANIMATION_KEYFRAME_STORYBOARD_START 미리 정의 된 값으로 설정 됩니다.|  
  
## <a name="remarks"></a>설명  
 UI_ANIMATION_KEYFRAME 변수를 캡슐화합니다. 모든 키 프레임 구현에 대 한 기본 클래스로 사용 됩니다. 키 프레임에 스토리 보드 내의 해당 시점의 나타내며 전환의 시작 시간과 종료 시간을 지정 하는 데 사용 될 합니다. 키프레임의-키프레임 (시간) 내에 지정된 된 오프셋에 스토리 보드에 추가 또는 지정 된 전환 후 추가 하는 방법은 두 종류가 있습니다. 애니메이션을 시작 하기 전에 일부 전환 기간을 알 수 없으므로 때문에 일부 키 프레임의 실제 값만 런타임에 결정 됩니다. 키 프레임 순서에는 키 프레임에 의존할 경우 전환에 종속 될 수 있으므로는 키 프레임 체인을 작성할 때 무한 재귀를 방지 해야 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseKeyFrame`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>CBaseKeyFrame::AddToStoryboard  
 스토리 보드에 키 프레임을 추가 합니다.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStoryboard`  
 스토리 보드에 대 한 포인터입니다.  
  
 `bDeepAdd`  
 이 매개 변수가 TRUE이 고 다른 키 프레임 또는 전환에 추가 되는 키 프레임에 따라 달라 집니다 하는 경우에이 메서드가이 키 프레임 또는 먼저 스토리 보드에 전환을 추가 하려고 합니다.  
  
### <a name="return-value"></a>반환 값  
 키 프레임 성공적으로 스토리 보드에 추가 되었으면 TRUE 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 스토리 보드에 키 프레임을 추가 합니다.  
  
##  <a name="cbasekeyframe"></a>CBaseKeyFrame::CBaseKeyFrame  
 키 프레임 개체를 만듭니다.  
  
```  
CBaseKeyFrame();
```  
  
##  <a name="getanimationkeyframe"></a>CBaseKeyFrame::GetAnimationKeyframe  
 기본 키 프레임 값을 반환합니다.  
  
```  
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 키 프레임입니다. 기본값은 UI_ANIMATION_KEYFRAME_STORYBOARD_START 합니다.  
  
### <a name="remarks"></a>설명  
 기본 키 프레임 값에 대 한 접근자입니다.  
  
##  <a name="isadded"></a>CBaseKeyFrame::IsAdded  
 키 프레임 스토리 보드에 추가 되었는지 여부를 지정 합니다.  
  
```  
BOOL IsAdded() const;  
```  
  
### <a name="return-value"></a>반환 값  
 키 프레임; 스토리 보드에 추가 되 면 TRUE 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 기본 클래스에서 IsAdded 항상 TRUE를 반환 하지만 파생된 클래스에서 재정의 됩니다.  
  
##  <a name="iskeyframeatoffset"></a>CBaseKeyFrame::IsKeyframeAtOffset  
 키 프레임 오프셋에서 또는 전환 후 스토리 보드에 추가할지 여부를 지정 합니다.  
  
```  
BOOL IsKeyframeAtOffset() const;  
```  
  
### <a name="return-value"></a>반환 값  
 일부 지정 된 오프셋 위치에 스토리 보드에 키 프레임을 추가 해야 하는 경우 TRUE입니다. FALSE 이면 키 프레임 일부 전환 후 스토리 보드에 추가 해야 합니다.  
  
### <a name="remarks"></a>설명  
 키 프레임 오프셋에서 스토리 보드에 추가할지 여부를 지정 합니다. 파생된 클래스에서 오프셋 또는 전환을 지정 해야 합니다.  
  
##  <a name="m_badded"></a>CBaseKeyFrame::m_bAdded  
 이 키 프레임에 스토리 보드에 추가 되었는지 여부를 지정 합니다.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_biskeyframeatoffset"></a>CBaseKeyFrame::m_bIsKeyframeAtOffset  
 이 키 프레임에서 다른 기존 키 프레임의 오프셋 또는 일부 전환의 끝에서 스토리 보드에 추가할지 여부를 지정 합니다.  
  
```  
BOOL m_bIsKeyframeAtOffset;  
```  
  
##  <a name="m_keyframe"></a>CBaseKeyFrame::m_keyframe  
 Windows 애니메이션 API 키 프레임을 나타냅니다. 키 프레임 초기화 되지 않은 UI_ANIMATION_KEYFRAME_STORYBOARD_START 미리 정의 된 값으로 설정 됩니다.  
  
```  
UI_ANIMATION_KEYFRAME m_keyframe;  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
