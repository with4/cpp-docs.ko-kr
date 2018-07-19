---
title: 'Cdatasource:: Open | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: a6d28bd1-799a-48ed-8993-5f82d1705b77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3196aa89426e895dd6b73b28ce197e8f271a0262
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097070"
---
# <a name="cdatasourceopen"></a>CDataSource::Open
사용 하 여 데이터 원본에 대 한 연결을 엽니다는 **CLSID**, **ProgID**, 또는 `CEnumerator` 모니커 또는 로케이터 대화 상자를 표시 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Open(const CLSID& clsid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1) throw();  


HRESULT Open(const CLSID& clsid,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0) throw();HRESULT Open(LPCTSTR szProgID,  
  DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1) throw();HRESULT Open(LPCTSTR szProgID,  
   LPCTSTR pName,  LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0) throw();  

HRESULT Open(const CEnumerator& enumerator,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1) throw();  

HRESULT Open(const CEnumerator& enumerator,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0) throw();  

HRESULT Open(HWND hWnd = GetActiveWindow(),  
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET) throw();

HRESULT Open(LPCWSTR szProgID,   
  DBPROPSET* pPropSet = NULL,   
   ULONG nPropertySets = 1) throw();

HRESULT Open(LPCSTR szProgID,   
   LPCTSTR pName,LPCTSTR pUserName = NULL,   
   LPCTSTR pPassword = NULL,   
   long nInitMode = 0) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `clsid`  
 [in] **CLSID** 데이터 공급자의입니다.  
  
 *pPropSet*  
 [in] 배열에 대 한 포인터 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 속성 및 값을 설정할 수를 포함 하는 구조체입니다. 참조 [속성 집합 및 속성 그룹](https://msdn.microsoft.com/en-us/library/ms713696.aspx) 에 *OLE DB Programmer's Reference* in the Windows SDK입니다.  
  
 *nPropertySets*  
 [in] 수가 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조체에 전달 된 *pPropSet* 인수입니다.  
  
 *pName*  
 [in] 연결할 데이터베이스의 이름입니다.  
  
 *pUserName*  
 [in] 사용자의 이름입니다.  
  
 *pPassword*  
 [in] 사용자의 암호입니다.  
  
 `nInitMode`  
 [in] 데이터베이스 초기화 모드입니다. 참조 [초기화 속성](https://msdn.microsoft.com/en-us/library/ms723127.aspx)에 *OLE DB Programmer's Reference* 올바른 초기화 모드 목록을 Windows sdk입니다. `nInitMode`가 0이면 연결을 여는 데 사용되는 속성 집합에 초기화 모드가 포함되지 않습니다.  
  
 `szProgID`  
 [in] 프로그램 식별자입니다.  
  
 `enumerator`  
 [in] A [CEnumerator](../../data/oledb/cenumerator-class.md) 를 호출자에 게 지정 하지 않을 때 연결을 열기 위해 모니커를 가져오는 데 사용 되는 개체는 **CLSID**합니다.  
  
 `hWnd`  
 [in] 대화 상자의 부모가 될 창의 핸들입니다. `hWnd` 매개 변수를 사용하는 함수 오버로드를 사용하면 서비스 구성 요소가 자동으로 호출됩니다. 자세한 내용은 설명을 참조하세요.  
  
 `dwPromptOptions`  
 [in] 표시할 로케이터 대화 상자의 스타일을 결정합니다. 가능한 값은 Msdasc.h를 참조하세요.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 `hWnd` 매개 변수를 사용하는 이 메서드 오버로드는 oledb32.dll에 있는 서비스 구성 요소를 사용하여 데이터 소스 개체를 엽니다. 이 DLL에는 리소스 풀링, 자동 트랜잭션 참여 등과 같은 서비스 구성 요소 기능의 구현이 들어 있습니다. 자세한 내용은 "OLE DB 서비스" 참조에서 OLE DB 프로그래머 참조에서 [ http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)합니다.  
  
 `hWnd` 매개 변수를 사용하지 않는 메서드 오버로드는 oledb32.dll에서 서비스 구성 요소를 사용하지 않고 데이터 소스 개체를 엽니다. A [CDataSource](../../data/oledb/cdatasource-class.md) 이러한 함수 오버 로드를 사용 하 여 열린 개체 구성 요소 서비스의 기능을 사용할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 OLE DB 템플릿을 사용하여 Jet 4.0 데이터 소스를 여는 방법을 보여 줍니다. Jet 데이터 소스를 OLE DB 데이터 소스로 처리합니다. 그러나를 호출 하 여 **열려** 두 개의 속성 집합이:에 대 한 **DBPROPSET_DBINIT** 용이고 다른 **DBPROPSET_JETOLEDB_DBINIT**을 설정할 수 있습니다,  **DBPROP_JETOLEDB_DATABASEPASSWORD**합니다.  
  
 [!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)
