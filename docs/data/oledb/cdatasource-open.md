---
title: "CDataSource::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataSource::Open"
  - "ATL.CDataSource.Open"
  - "CDataSource::Open"
  - "CDataSource.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open 메서드"
ms.assetid: a6d28bd1-799a-48ed-8993-5f82d1705b77
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CDataSource::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**CLSID**, **ProgID** 또는 `CEnumerator` 모니커를 사용하여 데이터 소스에 대한 연결을 열거나 사용자에게 로케이터 대화 상자를 표시합니다.  
  
## 구문  
  
```  
  
        HRESULT Open(  
   const CLSID& clsid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CLSID& clsid,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   HWND hWnd = GetActiveWindow( ),  
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET   
) throw( );  
HRESULT Open(   
   LPCWSTR szProgID,   
   DBPROPSET* pPropSet = NULL,   
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(   
   LPCSTR szProgID,   
   LPCTSTR pName,   
   LPCTSTR pUserName = NULL,   
   LPCTSTR pPassword = NULL,   
   long nInitMode = 0   
) throw( );  
```  
  
#### 매개 변수  
 `clsid`  
 \[in\] 데이터 공급자의 **CLSID**입니다.  
  
 *pPropSet*  
 \[in\] 설정할 속성 및 값을 포함하는 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조체의 배열에 대한 포인터입니다.  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]의 *OLE DB 프로그래머 참조*에서 [속성 집합 및 속성 그룹](https://msdn.microsoft.com/en-us/library/ms713696.aspx)을 참조하세요.  
  
 *nPropertySets*  
 \[in\] *pPropSet* 인수로 전달된 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조체 수입니다.  
  
 *pName*  
 \[in\] 연결할 데이터베이스의 이름입니다.  
  
 *pUserName*  
 \[in\] 사용자의 이름입니다.  
  
 *pPassword*  
 \[in\] 사용자의 암호입니다.  
  
 `nInitMode`  
 \[in\] 데이터베이스 초기화 모드입니다.  올바른 초기화 모드 목록을 보려면 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]의 *OLE DB 프로그래머 참조*에서 [초기화 속성](https://msdn.microsoft.com/en-us/library/ms723127.aspx)을 참조하세요.  `nInitMode`가 0이면 연결을 여는 데 사용되는 속성 집합에 초기화 모드가 포함되지 않습니다.  
  
 `szProgID`  
 \[in\] 프로그램 식별자입니다.  
  
 `enumerator`  
 \[in\] 호출자가 **CLSID**를 지정하지 않을 경우 연결을 열기 위해 모니커를 가져오는 데 사용되는 [CEnumerator](../../data/oledb/cenumerator-class.md) 개체입니다.  
  
 `hWnd`  
 \[in\] 대화 상자의 부모가 될 창의 핸들입니다.  `hWnd` 매개 변수를 사용하는 함수 오버로드를 사용하면 서비스 구성 요소가 자동으로 호출됩니다. 자세한 내용은 설명을 참조하세요.  
  
 `dwPromptOptions`  
 \[in\] 표시할 로케이터 대화 상자의 스타일을 결정합니다.  가능한 값은 Msdasc.h를 참조하세요.  
  
## 반환 값  
 표준 `HRESULT`입니다.  
  
## 설명  
 `hWnd` 매개 변수를 사용하는 이 메서드 오버로드는 oledb32.dll에 있는 서비스 구성 요소를 사용하여 데이터 소스 개체를 엽니다. 이 DLL에는 리소스 풀링, 자동 트랜잭션 참여 등과 같은 서비스 구성 요소 기능의 구현이 들어 있습니다.  자세한 내용은 OLE DB 프로그래머 참조\([http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)\)의 "OLE DB 서비스"를 참조하세요.  
  
 `hWnd` 매개 변수를 사용하지 않는 메서드 오버로드는 oledb32.dll에서 서비스 구성 요소를 사용하지 않고 데이터 소스 개체를 엽니다.  이러한 함수 오버로드를 사용하여 연 [CDataSource](../../data/oledb/cdatasource-class.md) 개체는 서비스 구성 요소의 기능을 사용할 수 없습니다.  
  
## 예제  
 다음 코드에서는 OLE DB 템플릿을 사용하여 Jet 4.0 데이터 소스를 여는 방법을 보여 줍니다.  Jet 데이터 소스를 OLE DB 데이터 소스로 처리합니다.  그러나 **Open**에 대한 호출에는 **DBPROPSET\_DBINIT** 및 **DBPROPSET\_JETOLEDB\_DBINIT**에 대해 하나씩 두 개의 속성 집합이 필요하므로 **DBPROP\_JETOLEDB\_DATABASEPASSWORD**를 설정할 수 있습니다.  
  
 [!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/CPP/cdatasource-open_1.cpp)]  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)