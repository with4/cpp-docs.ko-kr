---
title: CSettingsStore 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::Close
- AFXSETTINGSSTORE/CSettingsStore::CreateKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteValue
- AFXSETTINGSSTORE/CSettingsStore::Open
- AFXSETTINGSSTORE/CSettingsStore::Read
- AFXSETTINGSSTORE/CSettingsStore::Write
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStore [MFC], CSettingsStore
- CSettingsStore [MFC], Close
- CSettingsStore [MFC], CreateKey
- CSettingsStore [MFC], DeleteKey
- CSettingsStore [MFC], DeleteValue
- CSettingsStore [MFC], Open
- CSettingsStore [MFC], Read
- CSettingsStore [MFC], Write
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5ed7d1dad634d330ac857f52d6ef35ef36c9c9a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376895"
---
# <a name="csettingsstore-class"></a>CSettingsStore Class
Windows API 함수를 래핑하여 레지스트리에 액세스하는 데 사용할 수 있는 개체 지향 인터페이스를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSettingsStore : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSettingsStore::CSettingsStore](#csettingsstore)|`CSettingsStore` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSettingsStore::Close](#close)|열린 레지스트리 키를 닫습니다.|  
|[CSettingsStore::CreateKey](#createkey)|지정된 된 키를 열거나 존재 하지 않는 경우 만듭니다.|  
|[CSettingsStore::DeleteKey](#deletekey)|지정된 된 키와 모든 자식을 삭제합니다.|  
|[CSettingsStore::DeleteValue](#deletevalue)|열린 키의 지정된 된 값을 삭제합니다.|  
|[CSettingsStore::Open](#open)|지정 된 키를 엽니다.|  
|[CSettingsStore::Read](#read)|지정 된 키 값에 대 한 데이터를 검색합니다.|  
|[CSettingsStore::Write](#write)|열린 키 아래의 레지스트리 값을 씁니다.|  
  
## <a name="remarks"></a>설명  
 멤버 함수 `CreateKey` 및 `Open` 는 매우 유사 합니다. 레지스트리 키가 이미 있는 경우 `CreateKey` 및 `Open` 같은 방식으로 함수입니다. 그러나 레지스트리 키가 없는 경우, `CreateKey` 반면 만들 `Open` 오류 값을 반환 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는의 Open 및 읽기 메서드를 사용 하 여 `CSettingsStore` 클래스입니다. 이 코드 조각은의 일부인는 [도구 팁 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSettingsStore`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxsettingsstore.h  
  
##  <a name="close"></a>  CSettingsStore::Close  
 열린 레지스트리 키를 닫습니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>설명  
 기본적으로이 메서드는의 소멸자에서는 [CSettingsStore 클래스](../../mfc/reference/csettingsstore-class.md)합니다.  
  
##  <a name="createkey"></a>  CSettingsStore::CreateKey  
 레지스트리 키를 열거나 존재 하지 않는 경우 만듭니다.  
  
```  
virtual BOOL CreateKey(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pszPath`  
 만들거나 열을 키의 이름을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0 그렇지 않으면 0이 아닌 값입니다.  
  
### <a name="remarks"></a>설명  
 `CreateKey` 사용 하 여 `m_hKey` 레지스트리 조회의 루트 라고 합니다. 검색할 `pszPath` 의 하위 키로 `m_hKey`합니다. 키가 없는 경우 `CreateKey` 을 만듭니다. 그렇지 않으면 키를 엽니다. `CreateKey` 다음 설정 `m_hKey` 만들거나 열린 키에 있습니다.  
  
##  <a name="csettingsstore"></a>  CSettingsStore::CSettingsStore  
 
          `CSettngsStore` 개체를 만듭니다.  
  
```  
CSettingsStore(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bAdmin`  
 지정 하는 부울 매개 변수 여부는 `CSettingsStore` 개체 관리자 모드에서 작동 합니다.  
  
 [in] `bReadOnly`  
 지정 하는 부울 매개 변수 여부는 `CSettingsStore` 개체가 읽기 전용 모드에 만들어집니다.  
  
### <a name="remarks"></a>설명  
 경우 `bAdmin` 로 설정 된 `true`, `m_hKey` 멤버 변수가로 설정 된 `HKEY_LOCAL_MACHINE`합니다. 설정한 경우 `bAdmin` 를 `false`, `m_hKey` 로 설정 된 `HKEY_CURRENT_USER`합니다.  
  
 액세스 보안에 따라 달라 집니다는 `bReadOnly` 매개 변수입니다. 경우 `bReadonly` 은 `false`, 보안 액세스로 설정 됩니다 `KEY_ALL_ACCESS`합니다. 경우 `bReadyOnly` 은 `true`, 액세스 보안의 조합으로 설정 됩니다 `KEY_QUERY_VALUE, KEY_NOTIFY` 및 `KEY_ENUMERATE_SUB_KEYS`합니다. 레지스트리 함께 보안 액세스에 대 한 자세한 내용은 참조 [레지스트리 키의 보안 및 액세스 권한을](http://msdn.microsoft.com/library/windows/desktop/ms724878)합니다.  
  
 에 대 한 소멸자 `CSettingsStore` 해제 `m_hKey` 자동으로 합니다.  
  
##  <a name="deletekey"></a>  CSettingsStore::DeleteKey  
 레지스트리 키 및 모든 자식 노드를 삭제합니다.  
  
```  
virtual BOOL DeleteKey(
    LPCTSTR pszPath,  
    BOOL bAdmin = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pszPath`  
 삭제할 키의 이름입니다.  
  
 [in] `bAdmin`  
 삭제할 키의 위치를 지정 하는 스위치입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 있으면이 메서드는 실패는 `CSettingsStore` 개체가 읽기 전용 모드 인지 합니다.  
  
 경우 매개 변수 `bAdmin` 0 이면 `DeleteKey` 에서 삭제 하는 키에 대 한 검색 `HKEY_CURRENT_USER`합니다. 경우 `bAdmin` 이 값은 0 `DeleteKey` 에서 삭제 하는 키에 대 한 검색 `HKEY_LOCAL_MACHINE`합니다.  
  
##  <a name="deletevalue"></a>  CSettingsStore::DeleteValue  
 값을 삭제 `m_hKey`합니다.  
  
```  
virtual BOOL DeleteValue(LPCTSTR pszValue);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pszValue`  
 제거 하려면 값 필드를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="open"></a>  CSettingsStore::Open  
 레지스트리 키를 엽니다.  
  
```  
virtual BOOL Open(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pszPath`  
 레지스트리 키의 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 지정 된 키 성공적으로 열리면 설정 `m_hKey` 이 키의 핸들을 합니다.  
  
##  <a name="read"></a>  CSettingsStore::Read  
 레지스트리 키에서 값을 읽습니다.  
  
```  
virtual BOOL Read(
    LPCTSTR pszKey,  
    int& iVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    DWORD& dwVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CString& sVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CStringList& scStringList);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CStringArray& scArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CDWordArray& dwcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CWordArray& wcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CByteArray& bcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    LPPOINT& lpPoint);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CRect& rect);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    BYTE** ppData,  
    UINT* pBytes);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObList& list);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObject& obj);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObject*& pObj);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pszKey`  
 레지스트리에서 읽을 값의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
 [out] `iVal`  
 레지스트리 키에서 읽는 값을 받는 정수 변수에 대 한 참조입니다.  
  
 [out] `dwVal`  
 레지스트리 키에서 읽는 값을 수신 하는 32 비트 2 배 워드 변수 참조입니다.  
  
 [out] `sVal`  
 레지스트리 키에서 읽는 값을 받는 문자열 변수에 대 한 참조입니다.  
  
 [out] `scStringList`  
 레지스트리 키에서 읽는 값을 받는 문자열 목록 변수에 대 한 참조입니다.  
  
 [out] `scArray`  
 레지스트리 키에서 읽는 값을 받는 문자열 배열 변수에 대 한 참조입니다.  
  
 [out] `dwcArray`  
 레지스트리 키에서 읽는 값을 수신 하는 32 비트 2 배 워드 배열 변수 참조입니다.  
  
 [out] `wcArray`  
 레지스트리 키에서 읽는 값을 수신 하는 16 비트 단어 배열 변수 참조입니다.  
  
 [out] `bcArray`  
 레지스트리 키에서 읽는 값을 수신 하는 바이트 배열 변수 참조입니다.  
  
 [out] `lpPoint`  
 에 대 한 포인터에 대 한 참조는 `POINT` 는 레지스트리 키에서 읽는 구조체는 값입니다.  
  
 [out] `rect`  
 에 대 한 참조는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 레지스트리 키에서 읽은 값을 받는 변수입니다.  
  
 [out] `ppData`  
 값을 받는 데이터에 대 한 포인터에 대 한 포인터는 레지스트리 키에서 읽는 합니다.  
  
 [out] `pBytes`  
 부호 없는 정수 변수에 대 한 포인터입니다. 이 변수는 버퍼의 크기를 받는 `ppData` 를 가리킵니다.  
  
 [out] `list`  
 에 대 한 참조는 [CObList](../../mfc/reference/coblist-class.md) 레지스트리 키에서 읽은 값을 받는 변수입니다.  
  
 [out] `obj`  
 에 대 한 참조는 [CObject](../../mfc/reference/cobject-class.md) 레지스트리 키에서 읽은 값을 받는 변수입니다.  
  
 [out] `pObj`  
 에 대 한 포인터에 대 한 참조는 `CObject` 레지스트리 키에서 읽은 값을 받는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 `Read` 에 대 한 확인 `pszKey` 의 하위 키로 `m_hKey`합니다.  
  
##  <a name="write"></a>  CSettingsStore::Write  
 열린 키 아래의 레지스트리 값을 씁니다.  
  
```  
virtual BOOL Write(
    LPCTSTR pszKey,  
    int iVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    DWORD dwVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPCTSTR pszVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CStringList& scStringList);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CByteArray& bcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CStringArray& scArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CDWordArray& dwcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CWordArray& wcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    const CRect& rect);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPPOINT& lpPoint);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPBYTE pData,  
    UINT nBytes);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObList& list);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObject& obj);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObject* pObj);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pszKey`  
 설정할 값의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 [in] `iVal`  
 저장할 데이터를 포함 하는 정수 변수에 대 한 참조입니다.  
  
 [in] `dwVal`  
 저장할 데이터를 포함 하는 32 비트 2 배 워드 변수 참조입니다.  
  
 [in] `pszVal`  
 저장할 데이터를 포함 하는 null로 끝나는 문자열 변수에 대 한 포인터입니다.  
  
 [in] `scStringList`  
 에 대 한 참조는 [CStringList](../../mfc/reference/cstringlist-class.md) 저장할 데이터를 포함 된 변수입니다.  
  
 [in] `bcArray`  
 저장할 데이터를 포함 하는 바이트 배열 변수 참조입니다.  
  
 [in] `scArray`  
 저장할 데이터를 포함 하는 문자열 배열 변수 참조입니다.  
  
 [in] `dwcArray`  
 저장할 데이터를 포함 하는 32 비트 2 배 워드 배열 변수 참조입니다.  
  
 [in] `wcArray`  
 저장할 데이터를 포함 하는 16 비트 단어 배열 변수 참조입니다.  
  
 [in] `rect`  
 에 대 한 참조는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 저장할 데이터를 포함 된 변수입니다.  
  
 [in] `lpPoint`  
 에 대 한 포인터에 대 한 참조는 `POINT` 저장할 데이터를 포함 된 변수입니다.  
  
 [in] `pData`  
 저장할 데이터를 포함 하는 버퍼에 대 한 포인터입니다.  
  
 [in] `nBytes`  
 에 데이터를 바이트 단위로 크기를 지정 된 `pData` 매개 지점입니다.  
  
 [in] `list`  
 에 대 한 참조는 [CObList](../../mfc/reference/coblist-class.md) 저장할 데이터를 포함 된 변수입니다.  
  
 [in] `obj`  
 에 대 한 참조는 [CObject](../../mfc/reference/cobject-class.md) 저장할 데이터를 포함 된 변수입니다.  
  
 [in] `pObj`  
 에 대 한 포인터에 대 한 포인터는 `CObject` 저장할 데이터를 포함 된 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>설명  
 설정 해야 레지스트리에 쓰려면 `bReadOnly` 만들 때 0이 아닌 값으로는 [CSettingsStore](../../mfc/reference/csettingsstore-class.md) 개체입니다. 자세한 내용은 참조 [CSettingsStore::CSettingsStore](#csettingsstore)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)
