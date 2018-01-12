---
title: "CRowsetImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl
- ATL.CRowsetImpl
- ATL::CRowsetImpl
dev_langs: C++
helpviewer_keywords: CRowsetImpl class
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1ae1bb857353b72551e4766516c571c0091062d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetimpl-class"></a>CRowsetImpl 클래스
많은 구현 인터페이스의 여러 상속을 요구 하지 않고 표준 OLE DB 행 집합 구현을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   class T,  
   class Storage,  
   class CreatorClass,  
   class ArrayType = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class RowsetInterface = IRowsetImpl < T, IRowset >   
>  
class CRowsetImpl :    
   public CComObjectRootEx<CreatorClass::_ThreadModel>,   
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,   
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 되는 사용자의 클래스 `CRowsetImpl`합니다.  
  
 `Storage`  
 사용자 레코드 클래스입니다.  
  
 `CreatorClass`  
 행 집합;에 대 한 속성을 포함 하는 클래스 일반적으로 명령입니다.  
  
 `ArrayType`  
 이 클래스는 역할을 행 집합의 데이터에 대 한 저장소입니다. 이 매개 변수의 기본값은 `CAtlArray`, 필요한 기능을 지 원하는 모든 클래스에 것은 아니지만 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[NameFromDBID](../../data/oledb/crowsetimpl-namefromdbid.md)|문자열을 추출는 **DBID** 에 복사는 `bstr` 전달 합니다.|  
|[SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)|유효성을 검사 하 고 저장 된 **DBID**두 문자열의 s ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 및 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).|  
  
### <a name="overridable-methods"></a>재정의 가능한 메서드  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/crowsetimpl-getcolumninfo.md)|특정 클라이언트 요청에 대 한 열 정보를 검색합니다.|  
|[GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)|데이터 멤버에 문자열 값을 복사 하는 문자열 값을 포함 하는 매개 변수 중 하나 또는 둘 그리고 있다면 확인 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 및 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)합니다.|  
|[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md)|참조 하는 경우 중 하나 또는 둘 다에 확인 **DBID**s는 문자열 값을 포함 하 고이 경우 해당 데이터 멤버에 복사 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 및 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)|기본적으로는 `CAtlArray` 하려면 사용자 레코드 템플릿 인수에 있는 templatizes `CRowsetImpl`합니다. 다른 배열 형식 클래스를 변경 하 여 사용할 수는 `ArrayType` 템플릿 인수 `CRowsetImpl`합니다.|  
|[m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)|행 집합의 초기 명령이 들어 있습니다.|  
|[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)|행 집합의 초기 인덱스를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 `CRowsetImpl`정적 업캐스팅의 형태로 재정의 제공합니다. 메서드는 주어진된 행 집합은 명령 텍스트를 확인 하는 방식을 제어 합니다. 직접 만들 수도 `CRowsetImpl`-스타일 클래스를 늘려 구현 인터페이스 다중 상속 합니다. 구현이 제공 해야 하는 유일한 방법은 **Execute**합니다. Creator 메서드가 할에 대 한 다른 서명을 만드는 행 집합의 형식에 따라 필요한 **Execute**합니다. 예를 들어, 사용 하는 경우는 `CRowsetImpl`-스키마 행 집합을 구현 하는 클래스를 파생는 **Execute** 메서드는 다음 서명이 갖습니다.  
  
 `HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`  
  
 만들려는 경우는 `CRowsetImpl`-파생 클래스는 명령이 나 세션의 행 집합을 구현 하는 **Execute** 메서드는 다음 서명이 갖습니다.  
  
 `HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`  
  
 중 하나를 구현 하는 `CRowsetImpl`-파생 **Execute** 메서드 내부 데이터 버퍼를 채워야 ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)).  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h