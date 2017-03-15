---
title: "CRichEditDoc 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditDoc
dev_langs:
- C++
helpviewer_keywords:
- document/view architecture, rich edit controls
- OLE containers, rich edit
- documents, rich edit
- rich edit controls, OLE container
- CRichEditDoc class
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
caps.latest.revision: 24
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
ms.openlocfilehash: c7233c27c92c6dc689853e1913bb26f0bb5941fa
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditdoc-class"></a>CRichEditDoc 클래스
와 [CRichEditView](../../mfc/reference/cricheditview-class.md) 및 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), MFC의 문서 뷰 아키텍처 컨텍스트 내에서 rich edit 컨트롤의 기능을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CRichEditDoc : public COleServerDoc  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](#createclientitem)|문서의 정리를 수행 하기 위해 호출 합니다.|  
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|입력 스트림과 출력 서식 지정 정보에 포함 되는지 여부를 나타냅니다.|  
|[CRichEditDoc::GetView](#getview)|연결 된 검색 [CRichEditView](../../mfc/reference/cricheditview-class.md) 개체입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CRichEditDoc::m_bRTF](#m_brtf)|스트림 I/O 서식 지정이 포함 되는지 여부를 나타냅니다.|  
  
## <a name="remarks"></a>주의  
 "Rich edit 컨트롤"에 사용자 입력 하 고 텍스트를 편집 창입니다. 텍스트 문자와 단락 서식이 할당할 수 있으며 포함 된 OLE 개체를 포함할 수 있습니다. Rich edit 컨트롤 텍스트의 서식을 지정 하는 프로그래밍 인터페이스를 제공 합니다. 그러나 응용 프로그램 사용자에 게 서식 지정 작업을 제공 하는 데 필요한 사용자 인터페이스 구성 요소를 구현 해야 합니다.  
  
 `CRichEditView`텍스트와 텍스트의 서식 특성을 유지 관리합니다. `CRichEditDoc`보기에 있는 클라이언트 항목의 목록을 유지 관리 합니다. `CRichEditCntrItem`OLE 클라이언트 항목에 대 한 컨테이너 쪽 액세스를 제공합니다.  
  
 이 Windows 공용 컨트롤 (및 따라서는 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스)은 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수 있습니다.  
  
 서식 있는 편집 문서를 사용 하 여 MFC 응용 프로그램의 예를 들어 참조는 [워드 패드](../../visual-cpp-samples.md) 샘플 응용 프로그램입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrich.h  
  
##  <a name="a-namecreateclientitema--cricheditdoccreateclientitem"></a><a name="createclientitem"></a>CRichEditDoc::CreateClientItem  
 만들려면이 함수를 호출 하는 `CRichEditCntrItem` 이 문서에 추가 합니다.  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>매개 변수  
 *preo*  
 에 대 한 포인터는 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) 구조를 OLE 항목에 설명 합니다. 새 `CRichEditCntrItem` 이 OLE 항목 주위에 개체 생성 합니다. 경우 *preo* 는 **NULL**, 새 클라이언트 항목이 비어 있습니다.  
  
### <a name="return-value"></a>반환 값  
 새 포인터 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 이 문서에 추가 된 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 모든 OLE 초기화를 수행 하지 않습니다.  
  
 자세한 내용은 참조는 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetstreamformata--cricheditdocgetstreamformat"></a><a name="getstreamformat"></a>CRichEditDoc::GetStreamFormat  
 서식 있는 편집 내용을 스트리밍에 대 한 텍스트 형식을 결정 하려면이 함수를 호출 합니다.  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>반환 값  
 다음 플래그 중 하나입니다.  
  
- `SF_TEXT`Rich edit 컨트롤 서식 지정 정보를 유지 하지 않는 것을 나타냅니다.  
  
- `SF_RTF`Rich edit 컨트롤 서식 지정 정보를 유지 관리지 않습니다 나타냅니다.  
  
### <a name="remarks"></a>주의  
 반환 값은 기준의 [m_bRTF](#m_brtf) 데이터 멤버입니다. 이 함수는 반환 `SF_RTF` 경우 `m_bRTF` 는 **TRUE**고, 그렇지 않으면 `SF_TEXT`합니다.  
  
##  <a name="a-namegetviewa--cricheditdocgetview"></a><a name="getview"></a>CRichEditDoc::GetView  
 에 액세스 하려면이 함수를 호출 하는 [CRichEditView](../../mfc/reference/cricheditview-class.md) 개체와 연결 된 `CRichEditDoc` 개체입니다.  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CRichEditView` 문서와 연결 된 개체입니다.  
  
### <a name="remarks"></a>주의  
 텍스트 및 서식 지정 정보에 포함 된는 `CRichEditView` 개체입니다. `CRichEditDoc` 개체는 직렬화를 위한 OLE 항목을 유지 합니다. 하나만 있어야 `CRichEditView` 각 `CRichEditDoc`합니다.  
  
##  <a name="a-namembrtfa--cricheditdocmbrtf"></a><a name="m_brtf"></a>CRichEditDoc::m_bRTF  
 때 **TRUE**, 나타내는 [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) 및 [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) 단락 및 문자 서식 특성에 저장 해야 합니다.  
  
```  
BOOL m_bRTF;  
```  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 워드 패드](../../visual-cpp-samples.md)   
 [COleServerDoc 클래스](../../mfc/reference/coleserverdoc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRichEditView 클래스](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem 클래스](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument 클래스](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl 클래스](../../mfc/reference/cricheditctrl-class.md)

