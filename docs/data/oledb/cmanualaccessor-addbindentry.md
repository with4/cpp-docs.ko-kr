---
title: 'Cmanualaccessor:: Addbindentry | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- AddBindEntry
- CManualAccessor.AddBindEntry
dev_langs:
- C++
helpviewer_keywords:
- AddBindEntry method
ms.assetid: 8556dda9-dda1-4f67-96bc-6031e6c6a271
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5809773a6bcf8523f4b2cce07ca638c57e7c59bc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="cmanualaccessoraddbindentry"></a>CManualAccessor::AddBindEntry
출력 열에 바인딩 항목을 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```
void AddBindEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL) throw ();  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 `nOrdinal`  
 [in] 열 번호입니다.  
  
 `wType`  
 [in] 데이터 형식입니다.  
  
 `nColumnSize`  
 [in] 열 크기 (바이트)에서입니다.  
  
 `pData`  
 [in] 버퍼에 저장 된 열 데이터에 대 한 포인터입니다.  
  
 `pLength`  
 [in] 필요한 경우 필드 길이에 대 한 포인터입니다.  
  
 `pStatus`  
 [in] 필요한 경우 열 상태에 바인딩할 수를 변수에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 함수를 사용 하려면 호출 먼저 해야 [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)합니다. 에 지정 된 열의 수보다 더 많은 항목을 추가할 수 없습니다 `CreateAccessor`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)   
 [DBViewer 샘플](../../visual-cpp-samples.md)