---
title: "CKeyFrame 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CKeyFrame
- CKeyFrame
dev_langs:
- C++
helpviewer_keywords:
- CKeyFrame class
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d8ecff2e36148fb114ee708712b6e8bd0fe558ed
ms.lasthandoff: 02/24/2017

---
# <a name="ckeyframe-class"></a>CKeyFrame 클래스
애니메이션 키프레임을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CKeyFrame::CKeyFrame](#ckeyframe)|오버로드됨. 다른 키 프레임에 의존 하는 키 프레임을 생성 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|스토리 보드에 키 프레임을 추가합니다. (재정의 [CBaseKeyFrame::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|  
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|전환 후 스토리 보드에 키 프레임을 추가 합니다.|  
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|오프셋에서 스토리 보드에 키 프레임을 추가 합니다.|  
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|이 키 프레임에 따라 다릅니다. 키 프레임에 대 한 포인터를 반환 합니다.|  
|[CKeyFrame::GetOffset](#getoffset)|다른 키 프레임에서 오프셋을 반환합니다.|  
|[CKeyFrame::GetTransition](#gettransition)|이 키 프레임에 의존 변환에 대 한 포인터를 반환 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CKeyFrame::m_offset](#m_offset)|M_pExistingKeyFrame에 저장 된 키 프레임에서이 키 프레임의 오프셋을 지정 합니다.|  
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|기존 키프레임에 대에 대 한 포인터를 저장합니다. 이 키 프레임은 기존 키 프레임에 대 한 m_offset이 있는 스토리 보드에 추가 됩니다.|  
|[CKeyFrame::m_pTransition](#m_ptransition)|이 키 프레임에서 시작 하는 전환에 대 한 포인터를 저장 합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 애니메이션 키프레임을 구현합니다. 키 프레임 내 스토리 보드에에서 잠시 나타내고 전환의 시작 및 종료 시간을 지정 하는 데 사용 될 수 있습니다. 키 프레임 다른 키 프레임에 기반 할 수 있습니다 오프셋 (초), 또는 전환에 기반 할 수 있습니다 및를 시점에이 전환의 종료 시점을 나타냅니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxanimationcontroller.h  
  
##  <a name="a-nameaddtostoryboarda--ckeyframeaddtostoryboard"></a><a name="addtostoryboard"></a>CKeyFrame::AddToStoryboard  
 스토리 보드에 키 프레임을 추가합니다.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStoryboard`  
 스토리 보드에 대 한 포인터입니다.  
  
 `bDeepAdd`  
 키 프레임을 추가 또는 재귀적으로 전환할 것인지 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 키 프레임 추가 되었으면 TRUE입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 키프레임을 스토리 보드에 추가 합니다. 다른 키프레임 또는 전환에 따라 다릅니다 bDeepAdd TRUE 인 경우이 메서드를 재귀적으로 추가 하려고 시도 합니다.  
  
##  <a name="a-nameaddtostoryboardaftertransitiona--ckeyframeaddtostoryboardaftertransition"></a><a name="addtostoryboardaftertransition"></a>CKeyFrame::AddToStoryboardAfterTransition  
 전환 후 스토리 보드에 키 프레임을 추가 합니다.  
  
```  
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStoryboard`  
 스토리 보드에 대 한 포인터입니다.  
  
 `bDeepAdd`  
 전환 재귀적으로 추가 것인지 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 키 프레임 추가 되었으면 TRUE입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 키프레임을 전환 후 스토리 보드에 추가 하는 프레임 워크에서 호출 됩니다.  
  
##  <a name="a-nameaddtostoryboardatoffseta--ckeyframeaddtostoryboardatoffset"></a><a name="addtostoryboardatoffset"></a>CKeyFrame::AddToStoryboardAtOffset  
 오프셋에서 스토리 보드에 키 프레임을 추가 합니다.  
  
```  
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pStoryboard`  
 스토리 보드에 대 한 포인터입니다.  
  
 `bDeepAdd`  
 여부를 키 프레임을 추가 하려면이 키 프레임에 따라 달라 집니다 재귀적으로 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 키 프레임 추가 되었으면 TRUE입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 키프레임을 오프셋에서 스토리 보드에 추가 하는 프레임 워크에서 호출 됩니다.  
  
##  <a name="a-nameckeyframea--ckeyframeckeyframe"></a><a name="ckeyframe"></a>CKeyFrame::CKeyFrame  
 전환에 의존 하는 키 프레임을 생성 합니다.  
  
```  
CKeyFrame(CBaseTransition* pTransition);

 
CKeyFrame(
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>매개 변수  
 `pTransition`  
 전환에 대 한 포인터입니다.  
  
 `pKeyframe`  
 키 프레임에 대 한 포인터입니다.  
  
 `offset`  
 시간 (초) pKeyframe로 지정 된 키 프레임에서의 오프셋입니다.  
  
### <a name="remarks"></a>주의  
 생성 된 키 프레임은 지정한 전환이 끝날 때 시점을 storyboard 내에 나타냅니다.  
  
##  <a name="a-namegetexistingkeyframea--ckeyframegetexistingkeyframe"></a><a name="getexistingkeyframe"></a>CKeyFrame::GetExistingKeyframe  
 이 키 프레임에 따라 다릅니다. 키 프레임에 대 한 포인터를 반환 합니다.  
  
```  
CBaseKeyFrame* GetExistingKeyframe();
```  
  
### <a name="return-value"></a>반환 값  
 유효한 포인터 키프레임, 또는이 키 프레임 다른 키 프레임에 의존 하지 않는 경우 NULL입니다.  
  
### <a name="remarks"></a>주의  
 이 키 프레임에 따라 다릅니다. 키 프레임에 대 한 접근자입니다.  
  
##  <a name="a-namegetoffseta--ckeyframegetoffset"></a><a name="getoffset"></a>CKeyFrame::GetOffset  
 다른 키 프레임에서 오프셋을 반환합니다.  
  
```  
UI_ANIMATION_SECONDS GetOffset();
```  
  
### <a name="return-value"></a>반환 값  
 다른 키 프레임에서 초에서는 오프셋입니다.  
  
### <a name="remarks"></a>주의  
 다른 키 프레임에서 시간 (초)에 있는 오프셋을 확인 하려면이 메서드를 호출 해야 합니다.  
  
##  <a name="a-namegettransitiona--ckeyframegettransition"></a><a name="gettransition"></a>CKeyFrame::GetTransition  
 이 키 프레임에 의존 변환에 대 한 포인터를 반환 합니다.  
  
```  
CBaseTransition* GetTransition();
```  
  
### <a name="return-value"></a>반환 값  
 유효한 포인터 전환 또는이 키 프레임 전환에 의존 하지 않는 경우 NULL입니다.  
  
### <a name="remarks"></a>주의  
 이 키 프레임에 따라 달라 집니다 전환에 대 한 접근자입니다.  
  
##  <a name="a-namemoffseta--ckeyframemoffset"></a><a name="m_offset"></a>CKeyFrame::m_offset  
 M_pExistingKeyFrame에 저장 된 키 프레임에서이 키 프레임의 오프셋을 지정 합니다.  
  
```  
UI_ANIMATION_SECONDS m_offset;  
```  
  
##  <a name="a-namempexistingkeyframea--ckeyframempexistingkeyframe"></a><a name="m_pexistingkeyframe"></a>CKeyFrame::m_pExistingKeyFrame  
 기존 키프레임에 대에 대 한 포인터를 저장합니다. 이 키 프레임은 기존 키 프레임에 대 한 m_offset이 있는 스토리 보드에 추가 됩니다.  
  
```  
CBaseKeyFrame* m_pExistingKeyFrame;  
```  
  
##  <a name="a-namemptransitiona--ckeyframemptransition"></a><a name="m_ptransition"></a>CKeyFrame::m_pTransition  
 이 키 프레임에서 시작 하는 전환에 대 한 포인터를 저장 합니다.  
  
```  
CBaseTransition* m_pTransition;  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

