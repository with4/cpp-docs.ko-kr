---
title: CEnumeratorAccessor 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
- CEnumeratorAccessor.m_bIsParent
- ATL::CEnumeratorAccessor::m_bIsParent
- m_bIsParent
- ATL.CEnumeratorAccessor.m_bIsParent
- CEnumeratorAccessor::m_bIsParent
- ATL::CEnumeratorAccessor::m_nType
- CEnumeratorAccessor.m_nType
- CEnumeratorAccessor::m_nType
- ATL.CEnumeratorAccessor.m_nType
- m_nType
- ATL::CEnumeratorAccessor::m_szDescription
- CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szDescription
- ATL.CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szName
- ATL.CEnumeratorAccessor.m_szName
- m_szName
- ATL::CEnumeratorAccessor::m_szName
- CEnumeratorAccessor.m_szName
- CEnumeratorAccessor::m_szParseName
- ATL::CEnumeratorAccessor::m_szParseName
- m_szParseName
- CEnumeratorAccessor.m_szParseName
- ATL.CEnumeratorAccessor.m_szParseName
dev_langs:
- C++
helpviewer_keywords:
- CEnumeratorAccessor class
- m_bIsParent
- m_nType
- m_szDescription
- m_szName
- m_szParseName
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0836a09adac92300a8438a0433fda874e78bcb25
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339219"
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor 클래스
사용한 [CEnumerator](../../data/oledb/cenumerator-class.md) 열거자 행 집합에서 데이터를 액세스할 수 있습니다.  
  
## <a name="syntax"></a>구문

```cpp
class CEnumeratorAccessor  
```  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="members"></a>멤버  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_bIsParent](#bisparent)|있는지 여부를 나타내는 열거자 부모 열거자의 경우 행이 열거자는 변수입니다.|  
|[m_nType](#ntype)|행이 데이터 원본 또는 열거자를 설명 하는지 여부를 나타내는 변수입니다.|  
|[m_szDescription](#szdescription)|데이터 원본 또는 열거자의 설명입니다.|  
|[m_szName](#szname)|데이터 원본 또는 열거자의 이름입니다.|  
|[m_szParseName](#szparsename)|에 전달할 문자열 [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) 데이터 원본 또는 열거자에 대 한 모니커를 가져오려고 합니다.|  
  
## <a name="remarks"></a>설명  
 이 행 집합은 데이터 원본 및 현재 열거자에서 표시 되는 열거자 구성 됩니다.  
  
## <a name="bisparent"></a> Cenumeratoraccessor:: M_bisparent
있는지 여부를 나타내는 열거자 부모 열거자의 경우 행이 열거자는 변수입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
VARIANT_BOOL m_bIsParent;  
```  
  
### <a name="remarks"></a>설명  
 참조 [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/library/ms711200.aspx) 에 *OLE DB Programmer's Reference* 자세한 내용은 합니다. 

## <a name="ntype"></a> Cenumeratoraccessor:: M_ntype
행이 데이터 원본 또는 열거자를 설명 하는지 여부를 나타내는 변수입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
USHORT m_nType;  
```  
  
### <a name="remarks"></a>설명  
 참조 [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/library/ms711200.aspx) 에 *OLE DB Programmer's Reference* 자세한 내용은 합니다.

## <a name="szdescription"></a> Cenumeratoraccessor:: M_szdescription
데이터 원본 또는 열거자의 설명입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
WCHAR m_szDescription[129];  
```  
  
### <a name="remarks"></a>설명  
 참조 [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/library/ms711200.aspx) 에 *OLE DB Programmer's Reference* 자세한 내용은 합니다.

## <a name="szname"></a> Cenumeratoraccessor:: M_szname
데이터 원본 또는 열거자의 이름입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
WCHAR m_szName[129];  
```  
  
### <a name="remarks"></a>설명  
 참조 [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/library/ms711200.aspx) 에 *OLE DB Programmer's Reference* 자세한 내용은 합니다.  

## <a name="szparsename"></a> Cenumeratoraccessor:: M_szparsename
에 전달할 문자열 [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) 데이터 원본 또는 열거자에 대 한 모니커를 가져오려고 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
WCHAR m_szParseName[129];  
```  
  
### <a name="remarks"></a>설명  
 참조 [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/library/ms711200.aspx) 에 *OLE DB Programmer's Reference* 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)