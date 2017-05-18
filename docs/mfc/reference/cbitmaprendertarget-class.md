---
title: "CBitmapRenderTarget 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CBitmapRenderTarget class
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 11bea138185df23c9f3cc79491c71d86861a6bdc
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget 클래스
ID2D1BitmapRenderTarget에 대 한 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CBitmapRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|CBitmapRenderTarget 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CBitmapRenderTarget::Attach](#attach)|기존 연결 개체를 대상 인터페이스를 렌더링 합니다.|  
|[CBitmapRenderTarget::Detach](#detach)|렌더링 대상 인터페이스 개체에서 분리|  
|[CBitmapRenderTarget::GetBitmap](#getbitmap)|이 렌더링 대상에 대 한 비트맵을 검색합니다. 반환 된 비트맵 그리기 작업에 사용할 수 있습니다.|  
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|반환 ID2D1BitmapRenderTarget 인터페이스|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|반환 ID2D1BitmapRenderTarget 인터페이스|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CBitmapRenderTarget::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|ID2D1BitmapRenderTarget 개체에 대 한 포인터입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 `CBitmapRenderTarget` 
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="attach"></a>CBitmapRenderTarget::Attach  
 기존 연결 개체를 대상 인터페이스를 렌더링 합니다.  
  
```  
void Attach(ID2D1BitmapRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `pTarget`  
 기존 렌더링 대상 인터페이스입니다. NULL 일 수 없습니다.  
  
##  <a name="cbitmaprendertarget"></a>CBitmapRenderTarget::CBitmapRenderTarget  
 CBitmapRenderTarget 개체를 만듭니다.  
  
```  
CBitmapRenderTarget();
```  
  
##  <a name="detach"></a>CBitmapRenderTarget::Detach  
 렌더링 대상 인터페이스 개체에서 분리  
  
```  
ID2D1BitmapRenderTarget* Detach();
```  
  
### <a name="return-value"></a>반환 값  
 분리에 대 한 포인터는 대상 인터페이스를 렌더링 합니다.  
  
##  <a name="getbitmap"></a>CBitmapRenderTarget::GetBitmap  
 이 렌더링 대상에 대 한 비트맵을 검색합니다. 반환 된 비트맵 그리기 작업에 사용할 수 있습니다.  
  
```  
BOOL GetBitmap(CD2DBitmap& bitmap);
```  
  
### <a name="parameters"></a>매개 변수  
 `bitmap`  
 이 메서드가 반환 하는 경우에이 렌더링 대상에 대 한 유효한 비트맵이 포함 되어 있습니다. 이 비트맵 그리기 작업에 사용할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.  
  
##  <a name="getbitmaprendertarget"></a>CBitmapRenderTarget::GetBitmapRenderTarget  
 반환 ID2D1BitmapRenderTarget 인터페이스  
  
```  
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```  
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1BitmapRenderTarget 인터페이스에 대 한 포인터입니다.  
  
##  <a name="m_pbitmaprendertarget"></a>CBitmapRenderTarget::m_pBitmapRenderTarget  
 ID2D1BitmapRenderTarget 개체에 대 한 포인터입니다.  
  
```  
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;  
```  
  
##  <a name="operator_id2d1bitmaprendertarget_star"></a>CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *  
 반환 ID2D1BitmapRenderTarget 인터페이스  
  
```  
operator ID2D1BitmapRenderTarget*();
```   
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1BitmapRenderTarget 인터페이스에 대 한 포인터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

