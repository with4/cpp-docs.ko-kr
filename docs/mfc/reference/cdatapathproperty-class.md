---
title: "CDataPathProperty 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
dev_langs:
- C++
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4f258f5872a68931a40d21f7079e4089678baac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdatapathproperty-class"></a>CDataPathProperty 클래스
비동기적으로 로드할 수 있는 OLE 컨트롤 속성을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|`CDataPathProperty` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDataPathProperty::GetControl](#getcontrol)|와 연결 된 비동기 OLE 컨트롤을 검색 된 `CDataPathProperty` 개체입니다.|  
|[CDataPathProperty::GetPath](#getpath)|속성의 경로 이름을 검색합니다.|  
|[CDataPathProperty::Open](#open)|연결된 된 ActiveX (OLE) 컨트롤에 대 한 비동기 속성의 로딩을 시작 합니다.|  
|[CDataPathProperty::ResetData](#resetdata)|호출 `CAsyncMonikerFile::OnDataAvailable` 컨트롤 속성이 변경 되었습니다. 컨테이너를 알릴 수 있습니다.|  
|[CDataPathProperty::SetControl](#setcontrol)|속성과 연결 된 비동기 (OLE) ActiveX 컨트롤을 설정 합니다.|  
|[CDataPathProperty::SetPath](#setpath)|속성의 경로 이름을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 비동기 속성이 동기 시작 후 로드 됩니다.  
  
 클래스 `CDataPathProperty` 에서 파생 된 **CAysncMonikerFile**합니다. OLE 컨트롤의 비동기 속성을 구현 하려면에서 클래스를 파생 `CDataPathProperty`, 재정의 및 [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)합니다.  
  
 인터넷 응용 프로그램에서 비동기 모니커 및 ActiveX 컨트롤을 사용 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 합니다.  
  
- [인터넷 첫 번째 단계: ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md)  
  
- [인터넷 첫 번째 단계: 비동기 모니커](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h  
  
##  <a name="cdatapathproperty"></a>CDataPathProperty::CDataPathProperty  
 `CDataPathProperty` 개체를 생성합니다.  
  
```  
CDataPathProperty(COleControl* pControl = NULL);  
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pControl`  
 이 연결 될 OLE 컨트롤 개체에 대 한 포인터 `CDataPathProperty` 개체입니다.  
  
 `lpszPath`  
 절대 또는 상대 수 있는 경로를 실제 속성의 절대 위치를 참조 하는 비동기 모니커를 만드는 데 사용 합니다. `CDataPathProperty`Url, 하지 파일 이름을 사용합니다. 원하는 경우는 `CDataPathProperty` 파일에 대 한 개체를 앞에 추가 `file://` 경로에 있습니다.  
  
### <a name="remarks"></a>설명  
 `COleControl` 가리키는 개체 `pControl` ´ â **열려** 되 고 파생된 클래스에서 검색 합니다. 경우 `pControl` 은 **NULL**를 사용 하는 컨트롤 **열려** 으로 설정할지 `SetControl`합니다. 경우 `lpszPath` 은 **NULL**, 되는 경로에 전달할 수 있습니다 **열려** 사용 하 여 설정 하거나 `SetPath`합니다.  
  
##  <a name="getcontrol"></a>CDataPathProperty::GetControl  
 검색 하려면이 멤버 함수 호출의 `COleControl` 연관 된 개체는 `CDataPathProperty` 개체입니다.  
  
```  
COleControl* GetControl();
```  
  
### <a name="return-value"></a>반환 값  
 OLE 컨트롤에 대 한 포인터와 관련 된 반환 된 `CDataPathProperty` 개체입니다. **NULL** 하지 컨트롤이 연결 되어 있는 경우.  
  
##  <a name="getpath"></a>CDataPathProperty::GetPath  
 경로 검색, 경우에 설정 하려면이 함수를 호출는 `CDataPathProperty` 개체 생성 되었거나에 지정 된 **열려**, 또는 대 한 이전 호출에서 지정 된는 `SetPath` 멤버 함수입니다.  
  
```  
CString GetPath() const;  
```  
  
### <a name="return-value"></a>반환 값  
 속성 자체에 경로 이름을 반환합니다. 지정 된 경로가 없는 경우 비어 있을 수 있습니다.  
  
##  <a name="open"></a>CDataPathProperty::Open  
 연결된 된 컨트롤에 대 한 비동기 속성 로드를 시작 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual BOOL Open(
    COleControl* pControl,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    COleControl* pControl,
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    CFileException* pError = NULL);  
  
virtual BOOL Open(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pControl`  
 이 연결 될 OLE 컨트롤 개체에 대 한 포인터 `CDataPathProperty` 개체입니다.  
  
 `pError`  
 파일 예외에 대 한 포인터입니다. 오류 발생 시로 설정 됩니다 원인입니다.  
  
 `lpszPath`  
 절대 또는 상대 수 있는 경로를 실제 속성의 절대 위치를 참조 하는 비동기 모니커를 만드는 데 사용 합니다. `CDataPathProperty`Url, 하지 파일 이름을 사용합니다. 원하는 경우는 `CDataPathProperty` 파일에 대 한 개체를 앞에 추가 `file://` 경로에 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 가져오려고 시도 함수는 `IBindHost` 컨트롤에서 인터페이스입니다.  
  
 호출 하기 전에 **열려** 경로 없이 속성의 경로 대 한 값을 설정 해야 합니다. 이 개체가 생성 된, 또는 호출 하 여 때 수행할 수 있습니다는 `SetPath` 멤버 함수입니다.  
  
 호출 하기 전에 **열려** 없이 컨트롤 (이전의 OLE 컨트롤) ActiveX 컨트롤 개체와 연결할 수 있습니다. 개체가 생성 된, 또는 호출 하 여 때 이렇게 `SetControl`합니다.  
  
 모든 오버 로드 [CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open) 에서도 사용할 수 있는 `CDataPathProperty`합니다.  
  
##  <a name="resetdata"></a>CDataPathProperty::ResetData  
 가져오려면이 함수를 호출 `CAsyncMonikerFile::OnDataAvailable` 컨트롤 속성이 변경 되었으며 비동기적으로 로드 한 모든 정보를 더 이상 유용 하지 컨테이너를 알릴 수 없습니다.  
  
```  
virtual void ResetData();
```  
  
### <a name="remarks"></a>설명  
 열기를 다시 시작 해야 합니다. 파생된 클래스는 다른 기본값에 대 한이 함수를 재정의할 수 있습니다.  
  
##  <a name="setcontrol"></a>CDataPathProperty::SetControl  
 와 비동기 OLE 컨트롤을 연결 하려면이 멤버 함수 호출의 `CDataPathProperty` 개체입니다.  
  
```  
void SetControl(COleControl* pControl);
```  
  
### <a name="parameters"></a>매개 변수  
 `pControl`  
 속성에 연관 될 비동기 OLE 컨트롤에 대 한 포인터입니다.  
  
##  <a name="setpath"></a>CDataPathProperty::SetPath  
 속성의 경로 이름을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetPath(LPCTSTR lpszPath);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPath`  
 경로 절대 또는 상대 비동기적으로 로드 되는 속성을 수 있습니다. `CDataPathProperty`Url, 하지 파일 이름을 사용합니다. 원하는 경우는 `CDataPathProperty` 파일에 대 한 개체를 앞에 추가 `file://` 경로에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 이미지](../../visual-cpp-samples.md)   
 [CAsyncMonikerFile 클래스](../../mfc/reference/casyncmonikerfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile 클래스](../../mfc/reference/casyncmonikerfile-class.md)
