---
title: CArrayRowset 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CArrayRowset<TAccessor>
- ATL.CArrayRowset
- CArrayRowset
- ATL::CArrayRowset
- ATL::CArrayRowset<TAccessor>
- ATL::CArrayRowset::CArrayRowset
- CArrayRowset.CArrayRowset
- ATL.CArrayRowset.CArrayRowset
- ATL.CArrayRowset<TAccessor>.CArrayRowset
- CArrayRowset::CArrayRowset
- CArrayRowset
- CArrayRowset<TAccessor>::CArrayRowset
- ATL::CArrayRowset<TAccessor>::CArrayRowset
- CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset::Snapshot
- Snapshot
- CArrayRowset<TAccessor>::Snapshot
- ATL.CArrayRowset.Snapshot
- ATL.CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset<TAccessor>::Snapshot
- CArrayRowset::Snapshot
- CArrayRowset.Snapshot
- CArrayRowset::operator[]
- CArrayRowset.operator[]
- ATL::CArrayRowset::m_nRowsRead
- ATL::CArrayRowset<TAccessor>::m_nRowsRead
- CArrayRowset<TAccessor>::m_nRowsRead
- ATL.CArrayRowset<TAccessor>.m_nRowsRead
- CArrayRowset.m_nRowsRead
- m_nRowsRead
- ATL.CArrayRowset.m_nRowsRead
- CArrayRowset::m_nRowsRead
dev_langs:
- C++
helpviewer_keywords:
- CArrayRowset class
- CArrayRowset class, constructor
- Snapshot method
- operator [], arrays
- '[] operator'
- operator[], arrays
- m_nRowsRead
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3b367fc74fdbb03a6e5193f3fc9be08f74111a09
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207489"
---
# <a name="carrayrowset-class"></a>CArrayRowset 클래스
배열 구문을 사용 하 여 행 집합의 요소에 액세스 합니다.  
  
## <a name="syntax"></a>구문

```cpp
template < class TAccessor >  
class CArrayRowset :   
   public CVirtualBuffer <TAccessor>,   
   protected CBulkRowset <TAccessor>  
```  
  
### <a name="parameters"></a>매개 변수  
 *TAccessor*  
 사용 하 여 행 집합 접근자 클래스의 형식입니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CArrayRowset](#carrayrowset)|생성자입니다.|  
|[스냅숏](#snapshot)|전체 행 집합을 메모리로 읽습니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자&#91;&#93;](#operator)|행 집합의 요소에 액세스합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[CArrayRowset::m_nRowsRead](#nrowsread)|이미 읽은 행의 수입니다.|  
  
## <a name="carrayrowset"></a> Carrayrowset:: Carrayrowset
새 `CArrayRowset` 개체를 만듭니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
      CArrayRowset(int nMax = 100000);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *최대*  
 [in] 행 집합에 있는 최대 행 수입니다. 

## <a name="snapshot"></a> Carrayrowset:: Snapshot
전체 행 집합을 메모리로 읽어서 이에 대한 이미지 또는 스냅숏을 만듭니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
HRESULT Snapshot() throw();  
  
```  

## <a name="operator"></a> Carrayrowset:: Operator
행 집합의 행에 액세스 하는 것에 대 한 배열 유사 구문을 제공 합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
      TAccessor  
      & operator[](int nrow);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *TAccessor*  
 행 집합에 저장 하는 접근자의 유형을 지정 하는 템플릿 매개 변수입니다.  
  
 *nRow*  
 [in] 액세스 하려는 행 (배열 요소)의 수입니다.  
  
### <a name="return-value"></a>반환 값  
 요청한 행의 내용입니다.  
  
### <a name="remarks"></a>설명  
 하는 경우 *nRow* 행 집합의 행 수를 초과 하면, 예외가 throw 됩니다.  

## <a name="nrowsread"></a> Carrayrowset:: M_nrowsread
이미 읽은 행 집합의 행 수가 포함 되어 있습니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
ULONG m_nRowsRead;  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CRowset 클래스](../../data/oledb/crowset-class.md)