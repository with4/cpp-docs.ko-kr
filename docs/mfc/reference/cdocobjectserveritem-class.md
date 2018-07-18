---
title: CDocObjectServerItem 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
dev_langs:
- C++
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc498b96dad089276b248fbb2e420dde3c0bc514
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027140"
---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem 클래스
DocObject 서버 전용 OLE 서버 동사를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|`CDocObjectServerItem` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](#getdocument)|항목을 포함 하는 문서에 대 한 포인터를 검색 합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](#onhide)|DocObject 항목을 숨기려면 프레임 워크를 시도 하는 경우 예외가 throw 됩니다.|  
|[CDocObjectServerItem::OnShow](#onshow)|DocObject 항목 위치를 확인 하기 위해 프레임 워크에서 호출 활성화 합니다. 항목 DocObject 없으면 호출 [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)합니다.|  
  
## <a name="remarks"></a>설명  
 `CDocObjectServerItem` 재정의 가능한 멤버 함수를 정의 합니다. [OnHide](#onhide)를 [OnOpen](http://msdn.microsoft.com/7a9b1363-6ad8-4732-9959-4e35c07644fd), 및 [은 OnShow](#onshow)합니다.  
  
 사용 하도록 `CDocObjectServerItem`, 속하는 합니다 [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) 에서 재정의 `COleServerDoc`-파생된 클래스는 새 반환 `CDocObjectServerItem` 개체. 항목의 모든 기능을 변경 해야 하는 경우 자신만의 새 인스턴스를 만들 수 있습니다 `CDocObjectServerItem`-클래스를 파생 합니다.  
  
 참조에 대 한 자세한 내용은 DocObjects [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) 및 [COleCmdUI](../../mfc/reference/colecmdui-class.md) 에 *MFC 참조*합니다. 도 참조 하세요 [인터넷 첫 번째 단계: 활성 문서](../../mfc/active-documents-on-the-internet.md) 하 고 [액티브 문서](../../mfc/active-documents-on-the-internet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdocob.h  
  
##  <a name="cdocobjectserveritem"></a>  CDocObjectServerItem::CDocObjectServerItem  
 `CDocObjectServerItem` 개체를 생성합니다.  
  
```  
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>매개 변수  
 *pServerDoc*  
 새 DocObject 항목을 포함 하는 문서에 대 한 포인터입니다.  
  
 *bAutoDelete*  
 에 대 한 링크가 해제 될 때 개체를 삭제할 수 있는지 여부를 나타냅니다. 인수를 false로 설정 합니다 `CDocObjectServerItem` 개체는 문서의 데이터의 필수적인 부분입니다. 개체는 보조 구조는 프레임 워크에서 삭제할 수 있는 문서의 데이터에서 범위를 식별 하는 데 사용 하는 경우 TRUE로 설정 합니다.  
  
##  <a name="getdocument"></a>  CDocObjectServerItem::GetDocument  
 항목을 포함 하는 문서에 대 한 포인터를 검색 합니다.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항목을 포함 하는 문서에 대 한 포인터 항목이 문서의 일부가 아닌 경우 NULL입니다.  
  
### <a name="remarks"></a>설명  
 이 인수로 전달 하는 서버 문서에 대 한 액세스를 허용 합니다 [CDocObjectServerItem](#cdocobjectserveritem) 생성자입니다.  
  
##  <a name="onhide"></a>  CDocObjectServerItem::OnHide  
 항목을 숨기기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>설명  
 기본 구현 항목 DocObject 이면 예외가 throw 됩니다. 전체 뷰를 걸리기 때문에 액티브 DocObject 항목을 숨길 수 없습니다. DocObject 항목 상태가 아닙니다. 사라지게을 비활성화 해야 합니다. 기본 구현을 호출 하는 항목 DocObject 없으면 [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide)합니다.  
  
##  <a name="onshow"></a>  CDocObjectServerItem::OnShow  
 항목의 전체 DocObject 수 있도록 서버 응용 프로그램 프레임 워크에서 호출 활성화 합니다.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>설명  
 기본 구현을 호출 하는 항목 DocObject 없으면 [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen)합니다. 수행 하려는 특수 DocObject 항목을 열 때 처리 하는 경우이 함수를 재정의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [COleServerItem 클래스](../../mfc/reference/coleserveritem-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer 클래스](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem 클래스](../../mfc/reference/coledocobjectitem-class.md)
