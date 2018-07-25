---
title: CSession 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
- CSession.Abort
- CSession::Abort
- ATL.CSession.Abort
- ATL::CSession::Abort
- CSession::Close
- ATL.CSession.Close
- CSession.Close
- ATL::CSession::Close
- CSession.Commit
- ATL.CSession.Commit
- ATL::CSession::Commit
- CSession::Commit
- GetTransactionInfo
- CSession.GetTransactionInfo
- ATL.CSession.GetTransactionInfo
- CSession::GetTransactionInfo
- ATL::CSession::GetTransactionInfo
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
- CSession::StartTransaction
- StartTransaction
- ATL.CSession.StartTransaction
- CSession.StartTransaction
- ATL::CSession::StartTransaction
dev_langs:
- C++
helpviewer_keywords:
- CSession class
- Abort method
- Close method
- Commit method
- GetTransactionInfo method
- Open method
- StartTransaction method
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e60c08a982fe90b36c81e87b2bcc212ea11f5ed0
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233700"
---
# <a name="csession-class"></a>CSession 클래스
단일 데이터베이스 액세스 세션을 나타냅니다.  
  
## <a name="syntax"></a>구문

```cpp
class CSession  
```  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[중단](#abort)|취소 (종료) 트랜잭션.|  
|[닫기](#close)|세션을 닫습니다.|  
|[커밋](#commit)|트랜잭션을 커밋합니다.|  
|[GetTransactionInfo](#gettransactioninfo)|트랜잭션에 대 한 정보를 반환합니다.|  
|[열기](#open)|데이터 원본 개체에 대 한 새 세션을 엽니다.|  
|[StartTransaction](#starttransaction)|이 세션에 대 한 새 트랜잭션을 시작합니다.|  
  
## <a name="remarks"></a>설명  
 하나 이상의 세션으로 표현 되는 각 공급자 연결 (데이터 원본)를 사용 하 여 연결할 수는 [CDataSource](../../data/oledb/cdatasource-class.md) 개체입니다. 새로 만들 `CSession` 에 대 한는 `CDataSource`를 호출 [csession:: Open](../../data/oledb/csession-open.md)합니다. 데이터베이스 트랜잭션을 시작 하기 `CSession` 제공 된 `StartTransaction` 메서드. 트랜잭션이 시작 되 면 사용 하 여 커밋할 수 있습니다 합니다 `Commit` 메서드를 사용 하 여 취소 또는 `Abort` 메서드.  
  
## <a name="abort"></a> Csession:: Abort
트랜잭션을 종료합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
HRESULT Abort(BOID* pboidReason = NULL,   
   BOOL bRetaining = FALSE,   
   BOOL bAsync = FALSE) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [itransaction:: Abort](https://msdn.microsoft.com/library/ms709833.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT입니다. 

## <a name="close"></a> Csession:: Close
열려 있는 세션을 닫습니다 [csession:: Open](../../data/oledb/csession-open.md)합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
void Close() throw();  
  
```  
  
### <a name="remarks"></a>설명  
 릴리스는 `m_spOpenRowset` 포인터입니다.  

## <a name="commit"></a> Csession:: 커밋
트랜잭션을 커밋합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
HRESULT Commit(BOOL bRetaining = FALSE,   
   DWORD grfTC = XACTTC_SYNC,   
   DWORD grfRM = 0) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [itransaction:: Commit](https://msdn.microsoft.com/library/ms713008.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 [itransaction:: Commit](https://msdn.microsoft.com/library/ms713008.aspx)합니다.  

## <a name="gettransactioninfo"></a> Csession:: Gettransactioninfo
트랜잭션에 대 한 정보를 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
HRESULT GetTransactionInfo(XACTTRANSINFO* pInfo) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/library/ms714975.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/library/ms714975.aspx) 에 *OLE DB Programmer's Reference*합니다. 

## <a name="open"></a> Csession:: Open
데이터 원본 개체에 대 한 새 세션을 엽니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
HRESULT Open(const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *ds*  
 [in] 데이터 소스 세션을 열 수입니다.  
  
 *pPropSet*  
 [in] 배열에 대 한 포인터 [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) 속성 및 값을 설정할 수를 포함 하는 구조체. 참조 [속성 집합 및 속성 그룹](https://msdn.microsoft.com/library/ms713696.aspx) 에 *OLE DB Programmer's Reference* Windows SDK에에서 있습니다.  
  
 *ulPropSets*  
 [in] 수가 [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) 구조에 전달 합니다 *pPropSet* 인수입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 데이터 원본 개체를 열어야 [cdatasource:: Open](../../data/oledb/cdatasource-open.md) 전달 하기 전에 `CSession::Open`입니다.  

## <a name="starttransaction"></a> Csession:: Starttransaction
이 세션에 대 한 새 트랜잭션을 시작합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
HRESULT StartTransaction(ISOLEVEL isoLevel = ISOLATIONLEVEL_READCOMMITTED,  
   ULONG isoFlags = 0,  
   ITransactionOptions* pOtherOptions = NULL,  
   ULONG* pulTransactionLevel = NULL) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [itransactionlocal:: Starttransaction](https://msdn.microsoft.com/library/ms709786.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 [itransactionlocal:: Starttransaction](https://msdn.microsoft.com/library/ms709786.aspx) 에 *OLE DB Programmer's Reference*합니다. 
  
## <a name="see-also"></a>참고 항목  
 [CatDB](../../visual-cpp-samples.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)