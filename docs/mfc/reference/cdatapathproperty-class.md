---
title: "CDataPathProperty 클래스 | Microsoft 문서"
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
- ActiveX controls [C++], asynchronous
- OLE controls [C++], asynchronous
- CDataPathProperty class
- asynchronous controls [C++]
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d767cf950d8b86959aadc2fd4d77401134a6dc75
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
|[CDataPathProperty::Open](#open)|연결된 된 ActiveX (OLE) 컨트롤에 대 한 비동기 속성의 로드를 시작 합니다.|  
|[CDataPathProperty::ResetData](#resetdata)|호출 `CAsyncMonikerFile::OnDataAvailable` 컨트롤 속성이 변경 된 컨테이너를 알릴 수 있습니다.|  
|[CDataPathProperty::SetControl](#setcontrol)|속성과 연결 된 비동기 ActiveX (OLE) 제어를 설정 합니다.|  
|[CDataPathProperty::SetPath](#setpath)|속성의 경로 이름을 설정합니다.|  
  
## <a name="remarks"></a>주의  
 동기 초기화 한 다음 비동기 속성이 로드 됩니다.  
  
 클래스 `CDataPathProperty` 에서 파생 된 **CAysncMonikerFile**합니다. OLE 컨트롤에 비동기 속성을 구현 하려면에서 클래스를 파생 `CDataPathProperty`, 재정의 및 [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)합니다.  
  
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
 이 연결 되도록 OLE 컨트롤 개체에 대 한 포인터 `CDataPathProperty` 개체입니다.  
  
 `lpszPath`  
 절대 또는 상대 수 있는 경로를 속성의 실제 절대 위치를 참조 하는 비동기 모니커를 만드는 데 사용 합니다. `CDataPathProperty`Url을 하지 파일 이름을 사용합니다. 원하는 경우는 `CDataPathProperty` 파일에 대 한 개체를 앞에 추가 `file://` 경로에 있습니다.  
  
### <a name="remarks"></a>주의  
 `COleControl` 가리키는 개체 `pControl` 에서 사용 하는 **열려** 파생된 클래스에 의해 검색 됩니다. 경우 `pControl` 는 **NULL**를 사용 하는 컨트롤 **열려** 로 설정 해야 `SetControl`합니다. 경우 `lpszPath` 는 **NULL**를 통한 경로에 전달할 수 있습니다 **열려** 설정 또는 `SetPath`합니다.  
  
##  <a name="getcontrol"></a>CDataPathProperty::GetControl  
 검색 하려면이 멤버 함수를 호출의 `COleControl` 연관 된 개체는 `CDataPathProperty` 개체입니다.  
  
```  
COleControl* GetControl();
```  
  
### <a name="return-value"></a>반환 값  
 OLE 컨트롤에 대 한 포인터와 연결 된 반환 된 `CDataPathProperty` 개체입니다. **NULL** 하지 컨트롤이 연결 되어 있는 경우.  
  
##  <a name="getpath"></a>CDataPathProperty::GetPath  
 경로 검색, 경우에 설정 하려면이 멤버 함수를 호출는 `CDataPathProperty` 개체 생성 되었거나에 지정 된 **열려**에 대 한 이전 호출에 지정 된 또는 `SetPath` 멤버 함수입니다.  
  
```  
CString GetPath() const;  
```  
  
### <a name="return-value"></a>반환 값  
 속성 자체에 경로 반환합니다. 지정 된 경로가 없는 경우에 비어 있을 수 있습니다.  
  
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
 이 연결 되도록 OLE 컨트롤 개체에 대 한 포인터 `CDataPathProperty` 개체입니다.  
  
 `pError`  
 파일 예외에 대 한 포인터입니다. 오류 발생 시로 설정 됩니다 원인입니다.  
  
 `lpszPath`  
 절대 또는 상대 수 있는 경로를 속성의 실제 절대 위치를 참조 하는 비동기 모니커를 만드는 데 사용 합니다. `CDataPathProperty`Url을 하지 파일 이름을 사용합니다. 원하는 경우는 `CDataPathProperty` 파일에 대 한 개체를 앞에 추가 `file://` 경로에 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 가져오려고 시도 함수는 `IBindHost` 컨트롤에서 인터페이스입니다.  
  
 호출 하기 전에 **열려** 경로 없이 속성의 경로 대 한 값을 설정 합니다. 개체가 있으면 생성 된, 또는 호출 하 여 이렇게는 `SetPath` 멤버 함수입니다.  
  
 호출 하기 전에 **열려** 없이 컨트롤을 ActiveX 컨트롤 (이전의 OLE 컨트롤) 개체와 연결할 수 있습니다. 개체가 있으면 생성 된, 또는 호출 하 여 이렇게 `SetControl`합니다.  
  
 오버 로드를 모두 [CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open) 에서도 사용할 수 있는 `CDataPathProperty`합니다.  
  
##  <a name="resetdata"></a>CDataPathProperty::ResetData  
 가져오려면이 함수를 호출 `CAsyncMonikerFile::OnDataAvailable` 컨트롤 속성을 변경 하 고 비동기적으로 로드 한 모든 정보를 더 이상 유용 하지는 컨테이너를 알릴 수 없습니다.  
  
```  
virtual void ResetData();
```  
  
### <a name="remarks"></a>주의  
 열기를 다시 시작 해야 합니다. 파생된 클래스는 서로 다른 기본값에 대 한이 함수를 재정의할 수 있습니다.  
  
##  <a name="setcontrol"></a>CDataPathProperty::SetControl  
 와 비동기 OLE 컨트롤을 연결 하려면이 멤버 함수를 호출 하는 `CDataPathProperty` 개체입니다.  
  
```  
void SetControl(COleControl* pControl);
```  
  
### <a name="parameters"></a>매개 변수  
 `pControl`  
 속성은 연결 되도록 비동기 OLE 컨트롤에 대 한 포인터입니다.  
  
##  <a name="setpath"></a>CDataPathProperty::SetPath  
 속성의 경로 이름을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetPath(LPCTSTR lpszPath);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPath`  
 경로, 절대 또는 상대를 비동기적으로 로드 되 고 속성 될 수 있습니다. `CDataPathProperty`Url을 하지 파일 이름을 사용합니다. 원하는 경우는 `CDataPathProperty` 파일에 대 한 개체를 앞에 추가 `file://` 경로에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 이미지](../../visual-cpp-samples.md)   
 [CAsyncMonikerFile 클래스](../../mfc/reference/casyncmonikerfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile 클래스](../../mfc/reference/casyncmonikerfile-class.md)

