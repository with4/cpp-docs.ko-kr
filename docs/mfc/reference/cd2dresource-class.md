---
title: "CD2DResource 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DResource
- CD2DResource
dev_langs:
- C++
helpviewer_keywords:
- CD2DResource class
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
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
ms.openlocfilehash: b5a357a3653e2126de85b21efddca881c6c43a09
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dresource-class"></a>CD2DResource 클래스
만들고 브러시, 레이어 및 텍스트 같은 D2D 리소스를 관리 하기 위한 인터페이스를 제공 하는 추상 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DResource : public CObject;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DResource::CD2DResource](#cd2dresource)|CD2DResource 개체를 만듭니다.|  
|[CD2DResource:: ~ CD2DResource](#cd2dresource__~cd2dresource)|소멸자입니다. D2D 리소스 개체가 소멸 될 때 호출 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DResource::Create](#create)|CD2DResource를 만듭니다.|  
|[CD2DResource::Destroy](#destroy)|CD2DResource 개체를 소멸 시킵니다.|  
|[CD2DResource::IsValid](#isvalid)|리소스 유효성 검사|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DResource::IsAutoDestroy](#isautodestroy)|확인 자동 소멸 플래그입니다.|  
|[CD2DResource::ReCreate](#recreate)|CD2DResource를 다시 만듭니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DResource::m_bIsAutoDestroy](#m_bisautodestroy)|리소스는 소유자 (CRenderTarget)에 의해 파괴 됩니다.|  
|[CD2DResource::m_pParentTarget](#m_pparenttarget)|CRenderTarget 부모에 대 한 포인터)|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CD2DResource`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dresourcea--cd2dresourcecd2dresource"></a><a name="_dtorcd2dresource"></a>CD2DResource:: ~ CD2DResource  
 소멸자입니다. D2D 리소스 개체가 소멸 될 때 호출 됩니다.  
  
```  
virtual ~CD2DResource();
```  
  
##  <a name="a-namecd2dresourcea--cd2dresourcecd2dresource"></a><a name="cd2dresource"></a>CD2DResource::CD2DResource  
 CD2DResource 개체를 만듭니다.  
  
```  
CD2DResource(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentTarget`  
 렌더링 대상에 대 한 포인터입니다.  
  
 `bAutoDestroy`  
 개체 소유자 (pParentTarget)에 의해 소멸 되는 것을 나타냅니다.  
  
##  <a name="a-namecreatea--cd2dresourcecreate"></a><a name="create"></a>CD2DResource::Create  
 CD2DResource를 만듭니다.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pRenderTarget`  
 렌더링 대상에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK가 반환 됩니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.  
  
##  <a name="a-namedestroya--cd2dresourcedestroy"></a><a name="destroy"></a>CD2DResource::Destroy  
 CD2DResource 개체를 소멸 시킵니다.  
  
```  
virtual void Destroy() = 0;  
```  
  
##  <a name="a-nameisautodestroya--cd2dresourceisautodestroy"></a><a name="isautodestroy"></a>CD2DResource::IsAutoDestroy  
 확인 자동 소멸 플래그입니다.  
  
```  
BOOL IsAutoDestroy() const;  
```  
  
### <a name="return-value"></a>반환 값  
 개체의 소유자;에 의해 소멸 되 면 그렇지 않으면 FALSE입니다.  
  
##  <a name="a-nameisvalida--cd2dresourceisvalid"></a><a name="isvalid"></a>CD2DResource::IsValid  
 리소스 유효성 검사  
  
```  
virtual BOOL IsValid() const = 0;  
```  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 리소스는 올바르지 않습니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="a-namembisautodestroya--cd2dresourcembisautodestroy"></a><a name="m_bisautodestroy"></a>CD2DResource::m_bIsAutoDestroy  
 리소스는 소유자 (CRenderTarget)에 의해 파괴 됩니다.  
  
```  
BOOL m_bIsAutoDestroy;  
```  
  
##  <a name="a-namempparenttargeta--cd2dresourcempparenttarget"></a><a name="m_pparenttarget"></a>CD2DResource::m_pParentTarget  
 CRenderTarget 부모에 대 한 포인터)  
  
```  
CRenderTarget* m_pParentTarget;  
```  
  
##  <a name="a-namerecreatea--cd2dresourcerecreate"></a><a name="recreate"></a>CD2DResource::ReCreate  
 CD2DResource를 다시 만듭니다.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `pRenderTarget`  
 렌더링 대상에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK가 반환 됩니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

