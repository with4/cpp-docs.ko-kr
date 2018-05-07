---
title: CDocItem 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
dev_langs:
- C++
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 724e5017f51a3527e2ad81bcf707179053cc3e88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdocitem-class"></a>CDocItem 클래스
문서 데이터의 구성 요소로, 문서 항목에 대한 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDocItem::GetDocument](#getdocument)|항목이 포함 된 문서를 반환 합니다.|  
|[CDocItem::IsBlank](#isblank)|항목 정보를 포함 하는지 여부를 결정 합니다.|  
  
## <a name="remarks"></a>설명  
 `CDocItem` 개체는 클라이언트와 서버 문서에서 OLE 항목을 나타내는 데 사용 됩니다.  
  
 자세한 내용은 문서 참조 [컨테이너: 컨테이너 구현](../../mfc/containers-implementing-a-container.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="getdocument"></a>  CDocItem::GetDocument  
 항목이 포함 된 문서를 가져오려면이 함수를 호출 합니다.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항목이 포함 된 문서에 대 한 포인터 **NULL**항목이 문서의 일부가 아닌 경우, 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 파생된 클래스에서 재정의 되는 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 및 [COleServerItem](../../mfc/reference/coleserveritem-class.md), 포인터 중 하나를 반환 하는 [COleDocument](../../mfc/reference/coledocument-class.md), [ COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), 또는 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) 개체입니다.  
  
##  <a name="isblank"></a>  CDocItem::IsBlank  
 기본 serialization 발생할 때 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항목 정보를 포함 하지 않으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 `CDocItem` 개체는 비워 둘 수 없습니다. [COleClientItem](../../mfc/reference/coleclientitem-class.md) 에서 직접 파생 하기 때문에 개체는 비어 있는 경우에 따라 `CDocItem`합니다. 그러나 [COleServerItem](../../mfc/reference/coleserveritem-class.md) 개체는 항상 비어 있습니다. 기본적으로 포함 된 OLE 응용 프로그램 `COleClientItem` x 또는 y 없는 개체 익스텐트 serialize 됩니다. 반환 하 여 이렇게 **TRUE** 의 재정의에서 `IsBlank` 항목에 x 또는 y 범위입니다.  
  
 직렬화 하는 동안 다른 작업을 구현 하려는 경우이 함수를 재정의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDocument 클래스](../../mfc/reference/coledocument-class.md)   
 [COleServerItem 클래스](../../mfc/reference/coleserveritem-class.md)   
 [COleClientItem 클래스](../../mfc/reference/coleclientitem-class.md)
