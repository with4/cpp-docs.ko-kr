---
title: 'Ctable:: Open | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: 5d006d95-74d7-4e2b-b243-a33bc53b5455
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d727af84dfeae77ab08e57f2f3a11120f9f88631
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ctableopen"></a>CTable::Open
테이블을 엽니다.  
  
## <a name="syntax"></a>구문  
  
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
 `session`  
 [in] 세션 테이블이 열립니다.  
  
 *wszTableName*  
 [in] 를 열려면 테이블의 이름을 유니코드 문자열로 전달 합니다.  
  
 *szTableName*  
 [in] 를 열려면 테이블의 이름을 ANSI 문자열로 전달 합니다.  
  
 *dbid*  
 [in] **DBID** 열려는 테이블입니다.  
  
 *pPropSet*  
 [in] 배열에 대 한 포인터 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 속성 및 값을 설정할 수를 포함 하는 구조체입니다. 참조 [속성 집합 및 속성 그룹](https://msdn.microsoft.com/en-us/library/ms713696.aspx) 에 *OLE DB Programmer's Reference* in the Windows SDK입니다. 기본값은 NULL 없음 속성을 지정합니다.  
  
 `ulPropSets`  
 [in] 수가 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 구조체에 전달 된 *pPropSet* 인수입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 자세한 내용은 참조 하십시오. [iopenrowset:: Openrowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CTable 클래스](../../data/oledb/ctable-class.md)