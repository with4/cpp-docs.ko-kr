---
title: CRichEditCntrItem 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a64950bcb0cc931b4528276e85f5d60e3b5cb08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368422"
---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem 클래스
와 [CRichEditView](../../mfc/reference/cricheditview-class.md) 및 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), MFC의 문서 뷰 아키텍처 컨텍스트 내에서 rich edit 컨트롤의 기능을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|`CRichEditCntrItem` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|다른 형식으로 항목을 활성화합니다.|  
  
## <a name="remarks"></a>설명  
 "Rich edit 컨트롤"는 사용자 입력 수 있으며 텍스트를 편집 하는 창입니다. 텍스트 문자 및 단락 서식을 할당할 수 있으며 포함 된 OLE 개체를 포함할 수 있습니다. Rich edit 컨트롤 텍스트의 서식을 지정 하기 위한 프로그래밍 인터페이스를 제공 합니다. 그러나 응용 프로그램 사용자에 게 형식 지정 작업을 제공 하는 데 필요한 사용자 인터페이스 구성 요소를 구현 해야 합니다.  
  
 `CRichEditView` 텍스트 및 텍스트의 서식 특성을 유지 관리합니다. `CRichEditDoc` 보기에 있는 OLE 클라이언트 항목의 목록을 유지 관리 합니다. `CRichEditCntrItem` 컨테이너 쪽 OLE 클라이언트 항목에 대 한 액세스를 제공합니다.  
  
 이 Windows 공용 컨트롤 (및 따라서는 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 되는 프로그램에만 사용할 수는 있습니다.  
  
 MFC 응용 프로그램에서 서식 있는 편집 컨테이너 항목을 사용 하는 예제를 참조 하십시오.는 [워드 패드](../../visual-cpp-samples.md) 샘플 응용 프로그램입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [활성화](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrich.h  
  
##  <a name="cricheditcntritem"></a>  CRichEditCntrItem::CRichEditCntrItem  
 이 함수를 만드는 호출는 `CRichEditCntrItem` 컨테이너 문서에 추가 합니다.  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *preo*  
 에 대 한 포인터는 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE 항목에 설명 하는 구조입니다. 새 `CRichEditCntrItem` 이 OLE 항목 주위에 개체 생성 합니다. 경우 *preo* 은 **NULL**, 클라이언트 항목이 비어 있습니다.  
  
 `pContainer`  
 이 항목에 포함 될 컨테이너 문서에 대 한 포인터입니다. 경우 `pContainer` 은 **NULL**를 명시적으로 호출 해야 [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) 문서에이 클라이언트 항목을 추가 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 모든 OLE 초기화를 수행 하지 않습니다.  
  
 자세한 내용은 참조는 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Windows SDK에는 구조입니다.  
  
##  <a name="synctoricheditobject"></a>  CRichEditCntrItem::SyncToRichEditObject  
 장치 측면을 동기화 하려면이 함수를 호출 [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318),이 **CRichEditCntrltem** 에 지정 된 *reo*합니다.  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>매개 변수  
 *reo*  
 에 대 한 참조는 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE 항목에 설명 하는 구조입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [워드 패드 MFC 샘플](../../visual-cpp-samples.md)   
 [COleClientItem 클래스](../../mfc/reference/coleclientitem-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc 클래스](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView 클래스](../../mfc/reference/cricheditview-class.md)
