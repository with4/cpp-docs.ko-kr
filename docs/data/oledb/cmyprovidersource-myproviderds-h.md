---
title: CMyProviderSource (MyProviderDS.H) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- myproviderds.h
- cmyprovidersource
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderSource class in MyProviderDS.H
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0bdb766abd034868fe12fc0913fbdd99287b9e4f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cmyprovidersource-myproviderdsh"></a>CMyProviderSource(MyProviderDS.H)
공급자 클래스는 다중 상속을 사용합니다. 다음 코드에서는 데이터 원본 개체에 대 한 상속 체인을 보여 줍니다.  
  
```cpp
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSource  
class ATL_NO_VTABLE CMyProviderSource :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public CComCoClass<CMyProviderSource, &CLSID_MyProvider>,  
   public IDBCreateSessionImpl<CMyProviderSource, CMyProviderSession>,  
   public IDBInitializeImpl<CMyProviderSource>,  
   public IDBPropertiesImpl<CMyProviderSource>,  
   public IPersistImpl<CMyProviderSource>,  
   public IInternalConnectionImpl<CMyProviderSource>  
```  
  
 모든 COM 구성 요소에서 파생 `CComObjectRootEx` 및 `CComCoClass`합니다. `CComObjectRootEx` 에 대 한 모든 구현을 제공는 **IUnknown** 인터페이스입니다. 모든 스레딩 모델을 처리할 수 있습니다. `CComCoClass` 필요한 모든 오류 지원을 처리 합니다. 클라이언트에 자세한 오류 정보를 전송 하려는 경우 일부의 오류 Api 사용할 수 있습니다에 `CComCoClass`합니다.  
  
 데이터 원본 개체는 또한 여러 'Impl' 클래스에서 상속합니다. 각 클래스에는 인터페이스에 대 한 구현을 제공합니다. 데이터 원본 개체 구현 하는 `IPersist`, `IDBProperties`, **IDBInitialize**, 및 **IDBCreateSession** 인터페이스입니다. OLE DB 데이터 원본 개체를 구현 하려면 각 인터페이스가 필요 합니다. 상속 하거나이 'Impl' 클래스 중 하나에서 상속 하지 않고 하 여 특정 기능을 지원 하지 또는 지원 하도록 선택할 수 있습니다. 지원 하려는 경우는 **IDBDataSourceAdmin** 에서 상속 하는 인터페이스는 **IDBDataSourceAdminImpl** 필요한 기능을 활용 하려면 클래스입니다.  
  
## <a name="com-map"></a>COM 맵  
 클라이언트가 호출할 때마다 `QueryInterface` 데이터 원본에 대 한 인터페이스에 대해 다음과 같은 COM 맵을 통해 이동 합니다.  
  
```  
BEGIN_COM_MAP(CMyProviderSource)  
   COM_INTERFACE_ENTRY(IDBCreateSession)  
   COM_INTERFACE_ENTRY(IDBInitialize)  
   COM_INTERFACE_ENTRY(IDBProperties)  
   COM_INTERFACE_ENTRY(IPersist)  
   COM_INTERFACE_ENTRY(IInternalConnection)  
END_COM_MAP()  
```  
  
 COM_INTERFACE_ENTRY 매크로 ATL 가져온에서 것 이며의 구현을 알 `QueryInterface` 에 `CComObjectRootEx` 에 적절 한 인터페이스를 반환 합니다.  
  
## <a name="property-map"></a>속성 맵  
 속성 맵의 공급자가 지정 되는 모든 속성을 지정 합니다.  
  
```  
BEGIN_PROPSET_MAP(CMyProviderSource)  
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)  
      PROPERTY_INFO_ENTRY(ACTIVESESSIONS)  
      PROPERTY_INFO_ENTRY(ASYNCTXNABORT)  
      PROPERTY_INFO_ENTRY(ASYNCTXNCOMMIT)  
      PROPERTY_INFO_ENTRY(BYREFACCESSORS)  
      PROPERTY_INFO_ENTRY_VALUE(CATALOGLOCATION, DBPROPVAL_CL_START)  
      PROPERTY_INFO_ENTRY(CATALOGTERM)  
      PROPERTY_INFO_ENTRY(CATALOGUSAGE)  
      PROPERTY_INFO_ENTRY(COLUMNDEFINITION)  
      PROPERTY_INFO_ENTRY(CONCATNULLBEHAVIOR)  
      PROPERTY_INFO_ENTRY(DATASOURCENAME)  
      PROPERTY_INFO_ENTRY(DATASOURCEREADONLY)  
      PROPERTY_INFO_ENTRY(DBMSNAME)  
      PROPERTY_INFO_ENTRY(DBMSVER)  
      PROPERTY_INFO_ENTRY_VALUE(DSOTHREADMODEL, DBPROPVAL_RT_FREETHREAD)  
      PROPERTY_INFO_ENTRY(GROUPBY)  
      PROPERTY_INFO_ENTRY(HETEROGENEOUSTABLES)  
      PROPERTY_INFO_ENTRY(IDENTIFIERCASE)  
      PROPERTY_INFO_ENTRY(MAXINDEXSIZE)  
      PROPERTY_INFO_ENTRY(MAXROWSIZE)  
      PROPERTY_INFO_ENTRY(MAXROWSIZEINCLUDESBLOB)  
      PROPERTY_INFO_ENTRY(MAXTABLESINSELECT)  
      PROPERTY_INFO_ENTRY(MULTIPLEPARAMSETS)  
      PROPERTY_INFO_ENTRY(MULTIPLERESULTS)  
      PROPERTY_INFO_ENTRY(MULTIPLESTORAGEOBJECTS)  
      PROPERTY_INFO_ENTRY(MULTITABLEUPDATE)  
      PROPERTY_INFO_ENTRY(NULLCOLLATION)  
      PROPERTY_INFO_ENTRY(OLEOBJECTS)  
      PROPERTY_INFO_ENTRY(ORDERBYCOLUMNSINSELECT)  
      PROPERTY_INFO_ENTRY(OUTPUTPARAMETERAVAILABILITY)  
      PROPERTY_INFO_ENTRY(PERSISTENTIDTYPE)  
      PROPERTY_INFO_ENTRY(PREPAREABORTBEHAVIOR)  
      PROPERTY_INFO_ENTRY(PREPARECOMMITBEHAVIOR)  
      PROPERTY_INFO_ENTRY(PROCEDURETERM)  
      PROPERTY_INFO_ENTRY(PROVIDERNAME)  
      PROPERTY_INFO_ENTRY(PROVIDEROLEDBVER)  
      PROPERTY_INFO_ENTRY(PROVIDERVER)  
      PROPERTY_INFO_ENTRY(QUOTEDIDENTIFIERCASE)  
      PROPERTY_INFO_ENTRY(ROWSETCONVERSIONSONCOMMAND)  
      PROPERTY_INFO_ENTRY(SCHEMATERM)  
      PROPERTY_INFO_ENTRY(SCHEMAUSAGE)  
      PROPERTY_INFO_ENTRY(STRUCTUREDSTORAGE)  
      PROPERTY_INFO_ENTRY(SUBQUERIES)  
      PROPERTY_INFO_ENTRY(TABLETERM)  
      PROPERTY_INFO_ENTRY(USERNAME)  
   END_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)  
   BEGIN_PROPERTY_SET(DBPROPSET_DBINIT)  
      PROPERTY_INFO_ENTRY(AUTH_PASSWORD)  
      PROPERTY_INFO_ENTRY(AUTH_PERSIST_SENSITIVE_AUTHINFO)  
      PROPERTY_INFO_ENTRY(AUTH_USERID)  
      PROPERTY_INFO_ENTRY(INIT_DATASOURCE)  
      PROPERTY_INFO_ENTRY(INIT_HWND)  
      PROPERTY_INFO_ENTRY(INIT_LCID)  
      PROPERTY_INFO_ENTRY(INIT_LOCATION)  
      PROPERTY_INFO_ENTRY(INIT_MODE)  
      PROPERTY_INFO_ENTRY(INIT_PROMPT)  
      PROPERTY_INFO_ENTRY(INIT_PROVIDERSTRING)  
      PROPERTY_INFO_ENTRY(INIT_TIMEOUT)  
   END_PROPERTY_SET(DBPROPSET_DBINIT)  
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCE)  
      PROPERTY_INFO_ENTRY(CURRENTCATALOG)  
   END_PROPERTY_SET(DBPROPSET_DATASOURCE)  
   CHAIN_PROPERTY_SET(CMyProviderSession)  
END_PROPSET_MAP()  
```  
  
 OLE db에서 속성은 그룹화 됩니다. 데이터 원본 개체에는 두 그룹의 속성:에 대 한 하나는 **DBPROPSET_DATASOURCEINFO** 집합과 대 한은 **DBPROPSET_DBINIT** 설정 합니다. **DBPROPSET_DATASOURCEINFO** 집합 공급자와 데이터 원본에 대 한 속성에 해당 합니다. **DBPROPSET_DBINIT** 집합 초기화 시 사용 되는 속성에 해당 합니다. OLE DB 공급자 템플릿 PROPERTY_SET 매크로 함께 이러한 집합을 처리 합니다. 매크로 속성의 배열을 포함 하는 블록을 만듭니다. 클라이언트가 호출할 때마다는 `IDBProperties` 인터페이스를 공급자 속성 맵에 사용 합니다.  
  
 사양에서 모든 속성을 구현할 필요가 없습니다. 그러나; 필수 속성을 지원 해야 자세한 내용은 수준 0 규격 사양을 참조 하십시오. 속성을 지원 하지 않을 경우에 지도에서 제거할 수 있습니다. 속성을 지원 하려면 맵으로 PROPERTY_INFO_ENTRY 매크로 사용 하 여 추가 합니다. 에 해당 하는 매크로 **UPROPINFO** 다음 코드에 나와 있는 것 처럼 구조:  
  
```  
struct UPROPINFO  
{  
   DBPROPID    dwPropId;  
   ULONG       ulIDS;  
   VARTYPE     VarType;  
   DBPROPFLAGS dwFlags;  
   union  
   {  
      DWORD dwVal;  
      LPOLESTR szVal;  
   };  
   DBPROPOPTIONS dwOption;  
};  
```  
  
 구조에서 각 요소의 속성을 처리 하는 정보를 나타냅니다. 포함 된 한 **DBPROPID** 속성에 대 한 GUID 및 ID를 확인 하려면. 또한 유형 및 속성의 값을 결정 하는 항목이 포함 되어 있습니다.  
  
 (소비자가 언제 든 지 쓰기 가능한 속성의 값을 변경할 수 있는지 참고) 속성의 기본값을 변경 하려는 경우 PROPERTY_INFO_ENTRY_VALUE 또는 PROPERTY_INFO_ENTRY_EX 매크로 사용할 수 있습니다. 이러한 매크로 사용 하 여 해당 속성의 값을 지정할 수 있습니다. PROPERTY_INFO_ENTRY_VALUE 매크로 값을 변경할 수 있도록 줄임 표기입니다. PROPERTY_INFO_ENTRY_VALUE 매크로 PROPERTY_INFO_ENTRY_EX 매크로 호출합니다. 이 매크로 사용 하면 추가 하거나 모든 특성을 변경할 수 있습니다는 **UPROPINFO** 구조입니다.  
  
 고유한 속성 집합을 정의 하려는 경우에 추가 BEGIN_PROPSET_MAP/END_PROPSET_MAP 조합 하 여 하나 추가할 수 있습니다. 속성 집합의 GUID를 정의 하 고 다음 사용자 고유의 속성을 정의 해야 합니다. 공급자 관련 속성이 있는 경우 기존을 사용 하는 대신 설정 된 새 속성을 추가 합니다. 이후 버전의 OLE DB의 문제를 방지합니다.  
  
## <a name="user-defined-property-sets"></a>사용자 정의 속성 집합  
 Visual c + + 사용자 정의 속성 집합을 지원합니다. 재정의할 필요가 없습니다 **GetProperties** 또는 `GetPropertyInfo`합니다. 대신, 템플릿을 모든 사용자 정의 속성 집합을 검색 하 고 적절 한 개체에 추가 합니다.  
  
 초기화 시 사용할 수 있어야 하는 사용자 정의 속성 집합을 사용 하는 경우 (소비자를 호출 하기 전에, 즉 **idbinitialize:: Initialize**)를 사용 하 여이 지정할 수는 **UPROPSET_USERINIT** BEGIN_PROPERTY_SET_EX 매크로와 함께에서 플래그입니다. 속성 집합 (OLE DB 사양에는 다음이 필요 함)으로 작동 하려면이 옵션에 대 한 데이터 원본 개체에 있어야 합니다. 예:  
  
```  
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)  
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)  
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)  
```  
  
## <a name="see-also"></a>참고 항목  
 [공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)