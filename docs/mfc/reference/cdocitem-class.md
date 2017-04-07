---
title: "CDocItem 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
dev_langs:
- C++
helpviewer_keywords:
- items, document
- document items
- server documents, document items
- CDocItem class
- container document items
- client document items
- OLE documents, items
- server documents
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
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
ms.openlocfilehash: 1ade88aa562180d5c3a6a7afe3fe26943a5d811d
ms.lasthandoff: 02/24/2017

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
  
## <a name="remarks"></a>주의  
 `CDocItem`개체는 클라이언트와 서버 모두 문서에 OLE 항목을 나타내는 데 사용 됩니다.  
  
 자세한 내용은 문서를 참조 하십시오. [컨테이너: 컨테이너 구현](../../mfc/containers-implementing-a-container.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="getdocument"></a>CDocItem::GetDocument  
 항목을 포함 하는 문서를 가져오려면이 함수를 호출 합니다.  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항목이 포함 된 문서에 대 한 포인터 **NULL**항목 문서의 일부가 아닌 경우, 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 파생된 클래스에서 재정의 되는 [활성화](../../mfc/reference/coleclientitem-class.md) 및 [COleServerItem](../../mfc/reference/coleserveritem-class.md), 포인터 하나를 반환 하는 [COleDocument](../../mfc/reference/coledocument-class.md), [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), 또는 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) 개체입니다.  
  
##  <a name="isblank"></a>CDocItem::IsBlank  
 기본 serialization이 발생 하는 경우에 프레임 워크에서 호출 합니다.  
  
```  
virtual BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항목 정보를 포함 하지; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 `CDocItem` 개체는 비어 있습니다. [활성화](../../mfc/reference/coleclientitem-class.md) 에서 직접 파생 되므로 개체는 빈 때로는 `CDocItem`합니다. 그러나 [COleServerItem](../../mfc/reference/coleserveritem-class.md) 개체는 항상 비어 있습니다. 기본적으로 포함 된 OLE 응용 프로그램 `COleClientItem` x 또는 y 없는 개체 익스텐트 serialize 됩니다. 반환 하 여 이렇게 **TRUE** 재정의에서 `IsBlank` 때 항목에 x 또는 y 없습니다 범위입니다.  
  
 직렬화 하는 동안 다른 작업을 구현 하려는 경우이 함수를 재정의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDocument 클래스](../../mfc/reference/coledocument-class.md)   
 [COleServerItem 클래스](../../mfc/reference/coleserveritem-class.md)   
 [활성화 클래스](../../mfc/reference/coleclientitem-class.md)

