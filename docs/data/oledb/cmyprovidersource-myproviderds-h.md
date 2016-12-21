---
title: "CMyProviderSource(MyProviderDS.H) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ""myproviderds.h""
  - "cmyprovidersource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MyProviderDS.H의 CMyProviderSource 클래스"
  - "OLE DB 공급자, 마법사에서 생성된 파일"
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderSource(MyProviderDS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 공급자 클래스는 다중 상속을 사용합니다.  다음 코드는 데이터 소스 개체의 상속 체인을 보여 줍니다.  
  
```  
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
  
 모든 COM 구성 요소는 `CComObjectRootEx` 및 `CComCoClass`에서 파생됩니다.  `CComObjectRootEx`는 **IUnknown** 인터페이스에 대한 모든 구현을 제공합니다.  이 클래스는 모든 스레딩 모델을 처리할 수 있습니다.  `CComCoClass`는 필요한 모든 오류 지원을 처리합니다.  클라이언트에게 보다 자세한 오류 정보를 보내려면 `CComCoClass`의 몇 가지 오류 API를 사용합니다.  
  
 데이터 소스 개체도 몇몇 'Impl' 클래스에서 상속합니다.  각 클래스는 인터페이스 하나에 대한 구현을 제공합니다.  데이터 소스 개체는 `IPersist`, `IDBProperties`, **IDBInitialize** 및 **IDBCreateSession** 인터페이스를 구현합니다.  OLE DB가 데이터 소스 개체를 구현하려면 이러한 각 인터페이스가 필요합니다.  이러한 'Impl' 클래스 중 하나에서 상속하거나 상속하지 않음으로써 특정 기능을 지원할 수도 있고 지원하지 않을 수도 있습니다.  **IDBDataSourceAdmin** 인터페이스를 지원하려면 **IDBDataSourceAdminImpl** 클래스에서 상속하여 필요한 기능을 가져와야 합니다.  
  
## COM 맵  
 클라이언트가 데이터 소스의 인터페이스에 대해 `QueryInterface`를 호출할 때마다 클라이언트는 다음과 같은 COM 맵을 통과합니다.  
  
```  
BEGIN_COM_MAP(CMyProviderSource)  
   COM_INTERFACE_ENTRY(IDBCreateSession)  
   COM_INTERFACE_ENTRY(IDBInitialize)  
   COM_INTERFACE_ENTRY(IDBProperties)  
   COM_INTERFACE_ENTRY(IPersist)  
   COM_INTERFACE_ENTRY(IInternalConnection)  
END_COM_MAP()  
```  
  
 COM\_INTERFACE\_ENTRY 매크로는 ATL의 매크로이며 `CComObjectRootEx`의 `QueryInterface` 구현을 식별하여 적절한 인터페이스를 반환합니다.  
  
## 속성 맵  
 속성 맵은 공급자가 지정한 모든 속성을 명시합니다.  
  
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
  
 OLE DB의 속성은 그룹별로 나뉩니다.  데이터 소스 개체에는 **DBPROPSET\_DATASOURCEINFO** 집합과 **DBPROPSET\_DBINIT** 집합의 두 가지 속성 그룹이 있습니다.  **DBPROPSET\_DATASOURCEINFO** 집합은 공급자와 공급자의 데이터 소스에 대한 속성에 해당합니다.  **DBPROPSET\_DBINIT** 집합은 초기화에 사용되는 속성에 해당합니다.  OLE DB 공급자 템플릿은 PROPERTY\_SET 매크로를 사용하여 이러한 집합을 처리합니다.  이 매크로는 속성 배열이 있는 블록을 만들고,  클라이언트가 `IDBProperties` 인터페이스를 호출할 때마다 공급자는 이 속성 맵을 사용합니다.  
  
 사양의 모든 속성을 구현할 필요는 없지만,  필수 속성은 지원해야 합니다. 자세한 내용은 수준 0 규칙 사양을 참조하십시오.  지원하지 않을 속성은 맵에서 제거하면 됩니다.  지원할 속성이 있으면 PROPERTY\_INFO\_ENTRY 매크로를 사용하여 맵에 추가합니다.  이 매크로는 다음 코드의 **UPROPINFO** 구조에 해당합니다.  
  
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
  
 이 구조의 각 요소는 속성을 처리할 정보를 나타냅니다.  이 구조는 속성의 GUID와 ID를 결정하는 **DBPROPID**를 포함하며,  속성의 형식과 값을 결정하는 항목도 포함합니다.  
  
 소비자는 언제든지 쓰기 가능한 속성의 값을 변경할 수 있으므로 속성의 기본값을 변경하려면 PROPERTY\_INFO\_ENTRY\_VALUE나 PROPERTY\_INFO\_ENTRY\_EX 매크로를 사용합니다.  이 두 매크로를 사용하여 해당 속성의 값을 지정할 수 있습니다.  PROPERTY\_INFO\_ENTRY\_VALUE 매크로는 값을 변경할 수 있도록 하는 간단한 표기법입니다.  PROPERTY\_INFO\_ENTRY\_VALUE 매크로가 PROPERTY\_INFO\_ENTRY\_EX 매크로를 호출합니다.  이 매크로를 사용하여 **UPROPINFO** 구조에 특성을 추가하거나 모든 특성을 변경할 수 있습니다.  
  
 사용자 고유의 속성 집합을 정의하려면 BEGIN\_PROPSET\_MAP\/END\_PROPSET\_MAP 조합을 추가로 만들어 속성 집합을 추가합니다.  속성 집합의 GUID를 정의한 다음 사용자 고유 속성을 정의해야 합니다.  공급자 특정 속성이 있는 경우에는 기존 속성 대신 공급자 특정 속성을 새 속성 집합에 추가해야  이후 버전의 OLE DB에서 문제가 발생하는 것을 방지할 수 있습니다.  
  
## 사용자 정의 속성 집합  
 Visual C\+\+ .NET은 사용자 정의 속성 집합을 지원하므로  더 이상 **GetProperties**나 `GetPropertyInfo`를 재정의할 필요가 없습니다.  대신 사용자 정의 속성 집합이 있으면 템플릿이 이를 검색하여 적절한 개체에 추가합니다.  
  
 초기화할 때, 즉 소비자가 **IDBInitialize::Initialize**를 호출하기 전에 사용해야 할 사용자 정의 속성 집합이 있는 경우에는 BEGIN\_PROPERTY\_SET\_EX 매크로와 함께 **UPROPSET\_USERINIT** 플래그를 사용하여 이를 지정할 수 있습니다.  이렇게 하려면 OLE DB 사양에 명시된 대로 속성 집합이 데이터 소스 개체에 있어야 합니다.  예를 들면 다음과 같습니다.  
  
```  
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)  
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)  
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)  
```  
  
## 참고 항목  
 [공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)