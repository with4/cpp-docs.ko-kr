---
title: CD2DMesh 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DMesh
- AFXRENDERTARGET/CD2DMesh
- AFXRENDERTARGET/CD2DMesh::CD2DMesh
- AFXRENDERTARGET/CD2DMesh::Attach
- AFXRENDERTARGET/CD2DMesh::Create
- AFXRENDERTARGET/CD2DMesh::Destroy
- AFXRENDERTARGET/CD2DMesh::Detach
- AFXRENDERTARGET/CD2DMesh::Get
- AFXRENDERTARGET/CD2DMesh::IsValid
- AFXRENDERTARGET/CD2DMesh::Open
- AFXRENDERTARGET/CD2DMesh::m_pMesh
dev_langs:
- C++
helpviewer_keywords:
- CD2DMesh [MFC], CD2DMesh
- CD2DMesh [MFC], Attach
- CD2DMesh [MFC], Create
- CD2DMesh [MFC], Destroy
- CD2DMesh [MFC], Detach
- CD2DMesh [MFC], Get
- CD2DMesh [MFC], IsValid
- CD2DMesh [MFC], Open
- CD2DMesh [MFC], m_pMesh
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce3ad5cfa7df335b5633dffbdd221bf59f01bb29
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dmesh-class"></a>CD2DMesh 클래스
ID2D1Mesh에 대 한 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DMesh : public CD2DResource;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DMesh::CD2DMesh](#cd2dmesh)|CD2DMesh 개체를 만듭니다.|  
|[CD2DMesh:: ~ CD2DMesh](#_dtorcd2dmesh)|소멸자입니다. D2D 메시 개체가 소멸 될 때 호출 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DMesh::Attach](#attach)|기존 개체에 대 한 리소스 인터페이스를 연결.|  
|[CD2DMesh::Create](#create)|CD2DMesh를 만듭니다. (재정의 [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DMesh::Destroy](#destroy)|CD2DMesh 개체를 소멸 시킵니다. (재정의 [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DMesh::Detach](#detach)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DMesh::Get](#get)|반환 ID2D1Mesh 인터페이스|  
|[CD2DMesh::IsValid](#isvalid)|리소스 유효성 검사 (재정의 [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DMesh::Open](#open)|모집단에 대 한 메시를 엽니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DMesh::operator ID2D1Mesh *](#operator_id2d1mesh_star)|반환 ID2D1Mesh 인터페이스|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DMesh::m_pMesh](#m_pmesh)|ID2D1Mesh에 대 한 포인터입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DMesh`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="_dtorcd2dmesh"></a>  CD2DMesh:: ~ CD2DMesh  
 소멸자입니다. D2D 메시 개체가 소멸 될 때 호출 됩니다.  
  
```  
virtual ~CD2DMesh();
```  
  
##  <a name="attach"></a>  CD2DMesh::Attach  
 기존 개체에 대 한 리소스 인터페이스를 연결.  
  
```  
void Attach(ID2D1Mesh* pResource);
```  
  
### <a name="parameters"></a>매개 변수  
 `pResource`  
 기존 리소스 인터페이스입니다. NULL 일 수 없습니다.  
  
##  <a name="cd2dmesh"></a>  CD2DMesh::CD2DMesh  
 CD2DMesh 개체를 만듭니다.  
  
```  
CD2DMesh(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentTarget`  
 렌더링 대상에 대 한 포인터입니다.  
  
 `bAutoDestroy`  
 개체를 소유자 (pParentTarget)에 의해 폐기 수를 나타냅니다.  
  
##  <a name="create"></a>  CD2DMesh::Create  
 CD2DMesh를 만듭니다.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `pRenderTarget`  
 렌더링 대상에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.  
  
##  <a name="destroy"></a>  CD2DMesh::Destroy  
 CD2DMesh 개체를 소멸 시킵니다.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DMesh::Detach  
 개체에서 리소스 인터페이스를 분리합니다.  
  
```  
ID2D1Mesh* Detach();
```  
  
### <a name="return-value"></a>반환 값  
 분리 된 리소스 인터페이스 포인터입니다.  
  
##  <a name="get"></a>  CD2DMesh::Get  
 반환 ID2D1Mesh 인터페이스  
  
```  
ID2D1Mesh* Get();
```  
  
### <a name="return-value"></a>반환 값  
 ID2D1Mesh 인터페이스 또는 개체가 아직 초기화 되지 않은 경우에 NULL 포인터입니다.  
  
##  <a name="isvalid"></a>  CD2DMesh::IsValid  
 리소스 유효성 검사  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>반환 값  
 리소스 올바르면 TRUE입니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="m_pmesh"></a>  CD2DMesh::m_pMesh  
 ID2D1Mesh에 대 한 포인터입니다.  
  
```  
ID2D1Mesh* m_pMesh;  
```  
  
##  <a name="open"></a>  CD2DMesh::Open  
 모집단에 대 한 메시를 엽니다.  
  
```  
ID2D1TessellationSink* Open();
```  
  
### <a name="return-value"></a>반환 값  
 메시를 채우는 데 사용 되는 ID2D1TessellationSink에 대 한 포인터입니다.  
  
##  <a name="operator_id2d1mesh_star"></a>  CD2DMesh::operator ID2D1Mesh *  
 반환 ID2D1Mesh 인터페이스  
  
```  
operator ID2D1Mesh*();
```   
  
### <a name="return-value"></a>반환 값  
 ID2D1Mesh 인터페이스 또는 개체가 아직 초기화 되지 않은 경우에 NULL 포인터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
