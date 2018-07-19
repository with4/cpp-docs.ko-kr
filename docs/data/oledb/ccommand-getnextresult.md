---
title: 'Ccommand:: Getnextresult | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
dev_langs:
- C++
helpviewer_keywords:
- GetNextResult method
ms.assetid: 63df9b55-9490-45c4-934a-879c5c2725d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d833c3e644ac6ed44216542ce4fc6d995cc22efa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094197"
---
# <a name="ccommandgetnextresult"></a>CCommand::GetNextResult
다음 결과 집합 사용 가능한 경우 인출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,  
   bool bBind = true) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *pulRowsAffected*  
 [/ 출력] 명령에 의해 영향을 받는 행 수가 반환 되는 메모리에 대 한 포인터입니다.  
  
 `bBind`  
 [in] 실행 되 고 후 명령을 자동으로 바인딩할 것인지 지정 합니다. 기본값은 **true**, 때문에 명령을 자동으로 바인딩할 수 있습니다. 설정 `bBind` 를 **false** 수동으로 바인딩할 수 있도록 명령 자동 바인딩 방지 합니다. (수동 바인딩은 OLAP 사용자에 게 특히 중요 합니다.)  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 결과 집합을 이전에 가져온 경우이 함수는 이전 결과 집합을 해제 하 고 열을 바인딩 해제 합니다. 경우 `bBind` 은 **true**, 새 열을 바인딩합니다.  
  
 설정 하 여 여러 개의 결과 지정한 경우에이 함수를 호출 해야는 `CCommand` 템플릿 매개 변수 *TMultiple*=`CMultipleResults`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)