---
title: CCachedDataPathProperty 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
dev_langs:
- C++
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29e46f7e65d6c2f9b5c0d29007cd31f660754957
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355462"
---
# <a name="ccacheddatapathproperty-class"></a>CCachedDataPathProperty 클래스
비동기적으로 전송되고 메모리 파일에 캐싱되는 OLE 컨트롤 속성을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|`CCachedDataPathProperty` 개체를 생성합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile` 데이터를 캐시 하는 개체입니다.|  
  
## <a name="remarks"></a>설명  
 메모리 파일 아닌 디스크에 RAM에 저장 됩니다 및 빠른 임시 전송에 유용 합니다.  
  
 와 함께 **CAysncMonikerFile** 및 `CDataPathProperty`, `CCachedDataPathProperty` OLE 컨트롤에서 비동기 모니커를 사용 하기 위한 기능을 제공 합니다. 와 `CCachedDataPathProperty` URL 또는 파일 원본에서 데이터를 비동기적으로 전송 하 고를 통해 메모리 파일에 저장할 수 있는 개체는 `m_Cache` 공용 변수입니다. 모든 데이터는 메모리 파일에 저장 되 고 재정의할 필요가 없습니다 [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) 알림에 대 한 감시 하 고 응답 하는 경우가 있습니다. 예를 들어, 대용량 전송 하는 경우. GIF 파일 및 필요에 더 많은 데이터가 도착 하 고 자체를 그려야 컨트롤에 알리기 위해 재정의 `OnDataAvailable` 알림을 합니다.  
  
 클래스 `CCachedDataPathProperty` 에서 파생 된 `CDataPathProperty`합니다.  
  
 인터넷 응용 프로그램에서 비동기 모니커 및 ActiveX 컨트롤을 사용 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 합니다.  
  
- [인터넷 첫 번째 단계: ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md)  
  
- [인터넷 첫 번째 단계: 비동기 모니커](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h  
  
##  <a name="ccacheddatapathproperty"></a>  CCachedDataPathProperty::CCachedDataPathProperty  
 `CCachedDataPathProperty` 개체를 생성합니다.  
  
```  
CCachedDataPathProperty(COleControl* pControl = NULL);

 
CCachedDataPathProperty(
    LPCTSTR lpszPath,  
    COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pControl`  
 이 연결 될 ActiveX 컨트롤 개체에 대 한 포인터 `CCachedDataPathProperty` 개체입니다.  
  
 `lpszPath`  
 절대 또는 상대 수 있는 경로를 실제 속성의 절대 위치를 참조 하는 비동기 모니커를 만드는 데 사용 합니다. `CCachedDataPathProperty` Url, 하지 파일 이름을 사용합니다. 원하는 경우는 `CCachedDataPathProperty` 개체 파일에 대 한, file:// 경로 앞에 추가 합니다.  
  
### <a name="remarks"></a>설명  
 `COleControl` 가리키는 개체 `pControl` ´ â [열려](../../mfc/reference/cdatapathproperty-class.md#open) 되 고 파생된 클래스에서 검색 합니다. 경우 `pControl` 은 **NULL**를 사용 하는 컨트롤 **열려** 으로 설정할지 [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol)합니다. 경우 `lpszPath` 은 **NULL**, 되는 경로에 전달할 수 있습니다 **열려** 사용 하 여 설정 하거나 [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath)합니다.  
  
##  <a name="m_cache"></a>  CCachedDataPathProperty::m_Cache  
 데이터가 캐시 된 메모리 파일의 클래스 이름을 포함 합니다.  
  
```  
CMemFile m_Cache;  
```  
  
### <a name="remarks"></a>설명  
 메모리 파일은 RAM에 아닌 디스크에 저장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDataPathProperty 클래스](../../mfc/reference/cdatapathproperty-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty 클래스](../../mfc/reference/cdatapathproperty-class.md)
