---
title: 'Crowset:: Insert | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CRowset<TAccessor>.Insert
- CRowset.Insert
- CRowset<TAccessor>.Insert
- CRowset<TAccessor>::Insert
- ATL::CRowset<TAccessor>::Insert
- ATL.CRowset.Insert
- CRowset::Insert
- ATL::CRowset::Insert
dev_langs:
- C++
helpviewer_keywords:
- Insert method
ms.assetid: 6a64a1c3-10ac-4296-8685-0fd6fe63a13b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1e4ae63a867b0900712a90c880af1fc6c0329efe
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetinsert"></a>CRowset::Insert
만들고는 접근자의 데이터를에서 사용 하 여 새 행을 초기화 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT Insert(int nAccessor = 0,   
   bool bGetHRow = false) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nAccessor`  
 [in] 데이터 삽입에 사용할 접근자 수입니다.  
  
 *bGetHRow*  
 [in] 삽입된 된 행에 대 한 핸들을 검색 하는지 여부를 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용 하려면 선택적 인터페이스 `IRowsetChange`, 모든 공급자에서 지원 되지 않는 있는;의 경우이 메서드는 반환 **E_NOINTERFACE**합니다. 설정 해야 **DBPROP_IRowsetChange** 를 `VARIANT_TRUE` 호출 하기 전에 **열려** 테이블이 나 행 집합을 포함 하는 명령입니다.  
  
 하나 이상의 열에 쓸 수 없는 경우 삽입 실패할 수 있습니다. 이 문제를 해결하려면 커서 맵을 수정합니다.  
  
## <a name="example"></a>예  
 다음 예제에는 행 집합을 통해 데이터 원본에 액세스 한 다음 해당 행 집합의 테이블을 사용 하는 문자열을 삽입 하는 방법을 보여 줍니다.  
  
 먼저 프로젝트에 새 ATL 개체를 삽입 하 여 테이블 클래스를 만듭니다. 예를 들어, 작업 영역 창에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **새로운 ATL 개체**합니다. **데이터 액세스** 범주를 **소비자**합니다. 형식의 소비자 개체를 만들고 **테이블**합니다. (선택 **테이블** 테이블에서 직접 행 집합을 만듭니다; 선택 **명령** SQL 명령을 통해 행 집합을 만듭니다.) 해당 데이터 원본에 액세스할 수 있는 테이블을 지정 하는 데이터 원본을 선택 합니다. 소비자 개체를 호출할 경우 **CCustomerTable**, 삽입 코드를 다음과 같이 구현 합니다.  
  
 [!code-cpp[NVC_OLEDB_Consumer#10](../../data/oledb/codesnippet/cpp/crowset-insert_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)