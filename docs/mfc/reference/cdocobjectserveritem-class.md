---
title: "CDocObjectServerItem 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- document object server
- CDocObjectServerItem class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
caps.latest.revision: 22
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
ms.openlocfilehash: 06cf873512fbf43b729d9a70f185582a4e48cafc
ms.lasthandoff: 02/24/2017

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
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](#onhide)|프레임 워크 DocObject 항목을 숨기려면 하려고 하면 예외가 throw 됩니다.|  
|[CDocObjectServerItem::OnShow](#onshow)|항목 위치는 DocObject 있도록 프레임 워크에서 호출 활성화 합니다. DocObject는 항목이 없는 경우 호출 [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)합니다.|  
  
## <a name="remarks"></a>주의  
 `CDocObjectServerItem`재정의 가능한 멤버 함수를 정의: [OnHide](#onhide), [OnOpen](http://msdn.microsoft.com/en-us/7a9b1363-6ad8-4732-9959-4e35c07644fd), 및 [OnShow](#onshow)합니다.  
  
 사용 하 여 `CDocObjectServerItem`, 하는 [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) 에서 재정의할 프로그램 `COleServerDoc`-파생된 클래스는 새 반환 `CDocObjectServerItem` 개체입니다. 항목의 모든 기능을 변경 해야 할 경우 자신만의 새 인스턴스를 만들 수 있습니다 `CDocObjectServerItem`-클래스를 파생 합니다.  
  
 참조에 대 한 자세한 내용은 DocObjects [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) 및 [COleCmdUI](../../mfc/reference/colecmdui-class.md) 에 *MFC 참조*합니다. 또한 참조 [인터넷 첫 번째 단계: 활성 문서](../../mfc/active-documents-on-the-internet.md) 및 [액티브 문서](../../mfc/active-documents-on-the-internet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdocob.h  
  
##  <a name="cdocobjectserveritem"></a>CDocObjectServerItem::CDocObjectServerItem  
 `CDocObjectServerItem` 개체를 생성합니다.  
  
```  
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>매개 변수  
 `pServerDoc`  
 새 DocObject 항목을 포함 하는 문서에 대 한 포인터입니다.  
  
 `bAutoDelete`  
 에 대 한 링크가 해제 될 때 개체를 삭제할 수 있는지 여부를 나타냅니다. 인수를 설정 **FALSE** 경우는 `CDocObjectServerItem` 개체는 문서의 데이터의 필수적인 부분입니다. 로 설정 **TRUE** 개체가 프레임 워크에서 삭제할 수 있는 문서의 데이터의 범위를 식별 하는 데 사용 되는 보조 구조입니다.  
  
##  <a name="getdocument"></a>CDocObjectServerItem::GetDocument  
 항목을 포함 하는 문서에 대 한 포인터를 검색 합니다.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항목이 포함 된 문서에 대 한 포인터 **NULL** 항목 문서의 일부가 아닌 경우.  
  
### <a name="remarks"></a>주의  
 그러면에 인수로 전달 되는 서버 문서에 액세스할 수는 [CDocObjectServerItem](#cdocobjectserveritem) 생성자입니다.  
  
##  <a name="onhide"></a>CDocObjectServerItem::OnHide  
 항목을 숨기려면 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>주의  
 기본 구현은 항목이 DocObject 이면 예외가 throw 됩니다. 전체 뷰를 가져오므로 액티브 DocObject 항목을 숨길 수 없습니다. DocObject 항목 사라지게 할을 비활성화 해야 합니다. 기본 구현에서는 호출 하는 항목 DocObject 없으면 [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide)합니다.  
  
##  <a name="onshow"></a>CDocObjectServerItem::OnShow  
 서버 응용 프로그램의 DocObject 항목 위치를 지시 하는 프레임 워크에서 호출 활성화 합니다.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 호출 하는 항목 DocObject 없으면 [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen)합니다. 특수 처리 DocObject 항목을 열 때 수행 해야 할 경우이 함수를 재정의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [COleServerItem 클래스](../../mfc/reference/coleserveritem-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer 클래스](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem 클래스](../../mfc/reference/coledocobjectitem-class.md)

