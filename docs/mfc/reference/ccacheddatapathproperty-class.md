---
title: "CCachedDataPathProperty 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- CCachedDataPathProperty class
- OLE controls [C++], asynchronous
- asynchronous controls [C++]
- memory files [C++]
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
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
ms.openlocfilehash: 6e3f54e6429456be24cbe18471abd1705bbe0034
ms.lasthandoff: 02/24/2017

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
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile`데이터를 캐시 하는 개체입니다.|  
  
## <a name="remarks"></a>주의  
 메모리 파일을 RAM에 아닌 디스크에 저장 하 고 빠른 임시 전송에 유용 합니다.  
  
 와 함께 **CAysncMonikerFile** 및 `CDataPathProperty`, `CCachedDataPathProperty` OLE 컨트롤에서 비동기 모니커 사용에 대 한 기능을 제공 합니다. 와 `CCachedDataPathProperty` URL 또는 파일 원본에서 데이터를 비동기적으로 전송 하 고을 통해 메모리 파일에 저장할 수 있는 개체는 `m_Cache` 공용 변수입니다. 모든 데이터의 메모리 파일에 저장 되 고 재정의할 필요가 없습니다 [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) 알림을 확인 하 고 응답 하는 경우가 있습니다. 예를 들어, 대형 전송 하는 경우. GIF 파일 및 더 많은 데이터가 도착 하 고 자체를 다시 그릴 것인지 사용자 컨트롤에 알리기 위해 원하는 재정의 `OnDataAvailable` 알림을 합니다.  
  
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
  
##  <a name="a-nameccacheddatapathpropertya--ccacheddatapathpropertyccacheddatapathproperty"></a><a name="ccacheddatapathproperty"></a>CCachedDataPathProperty::CCachedDataPathProperty  
 `CCachedDataPathProperty` 개체를 생성합니다.  
  
```  
CCachedDataPathProperty(COleControl* pControl = NULL);

 
CCachedDataPathProperty(
    LPCTSTR lpszPath,  
    COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pControl`  
 이 연결 되도록 ActiveX 컨트롤 개체에 대 한 포인터 `CCachedDataPathProperty` 개체입니다.  
  
 `lpszPath`  
 절대 또는 상대 수 있는 경로를 속성의 실제 절대 위치를 참조 하는 비동기 모니커를 만드는 데 사용 합니다. `CCachedDataPathProperty`Url을 하지 파일 이름을 사용합니다. 원하는 경우는 `CCachedDataPathProperty` 파일에 대 한 개체, file:// 경로 앞에 추가 합니다.  
  
### <a name="remarks"></a>주의  
 `COleControl` 가리키는 개체 `pControl` 에서 사용 하는 [열려](../../mfc/reference/cdatapathproperty-class.md#open) 파생된 클래스에 의해 검색 됩니다. 경우 `pControl` 는 **NULL**를 사용 하는 컨트롤 **열려** 로 설정 해야 [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol)합니다. 경우 `lpszPath` 는 **NULL**를 통한 경로에 전달할 수 있습니다 **열려** 설정 또는 [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath)합니다.  
  
##  <a name="a-namemcachea--ccacheddatapathpropertymcache"></a><a name="m_cache"></a>CCachedDataPathProperty::m_Cache  
 데이터가 캐시 된 메모리 파일의 클래스 이름을 포함 합니다.  
  
```  
CMemFile m_Cache;  
```  
  
### <a name="remarks"></a>주의  
 메모리 파일을 RAM에 아니라 디스크에 저장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDataPathProperty 클래스](../../mfc/reference/cdatapathproperty-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty 클래스](../../mfc/reference/cdatapathproperty-class.md)

