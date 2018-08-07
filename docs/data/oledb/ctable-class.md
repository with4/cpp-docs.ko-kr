---
title: CTable 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CTable
- ATL.CTable
- CTable
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
dev_langs:
- C++
helpviewer_keywords:
- CTable class
- Open method
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 723d4f1e8f44c3ce376b4f39f34a191265ca4eab
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336728"
---
# <a name="ctable-class"></a>CTable 클래스
단순 행 집합 (매개 변수 없이 하나)에 직접 액세스할 수 있는 방법을 제공 합니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class TAccessor = CNoAccessor, 
            template <typename T> class TRowset = CRowset>  
class CTable :  
   public CAccessorRowset <TAccessor, TRowset>  
```  
  
### <a name="parameters"></a>매개 변수  
 *TAccessor*  
 접근자 클래스입니다.  
  
 *TRowset*  
 행 집합 클래스입니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[열기](#open)|테이블을 엽니다.|  
  
## <a name="remarks"></a>설명  
 참조 [CCommand](../../data/oledb/ccommand-class.md) 행 집합에 액세스 하는 명령을 실행 하는 방법에 대 한 정보에 대 한 합니다.  

## <a name="open"></a> Ctable:: Open
테이블을 엽니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  

HRESULT Open(const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  

HRESULT Open(const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *세션*  
 [in] 테이블 열려 있는 세션입니다.  
  
 *wszTableName*  
 [in] 를 열려면 테이블의 이름을 유니코드 문자열로 전달 합니다.  
  
 *szTableName*  
 [in] 를 열려면 테이블의 이름을 ANSI 문자열로 전달 합니다.  
  
 *dbid*  
 [in] `DBID` 열려는 테이블입니다.  
  
 *pPropSet*  
 [in] 배열에 대 한 포인터 [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) 속성 및 값을 설정할 수를 포함 하는 구조체. 참조 [속성 집합 및 속성 그룹](https://msdn.microsoft.com/library/ms713696.aspx) 에 *OLE DB Programmer's Reference* Windows SDK에에서 있습니다. 기본값은 NULL 없는 속성을 지정합니다.  
  
 *ulPropSets*  
 [in] 수가 [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) 구조에 전달 합니다 *pPropSet* 인수입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 하세요. [iopenrowset:: Openrowset](https://msdn.microsoft.com/library/ms716724.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   