---
title: 'Crowset:: Getdatahere | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset<TAccessor>::GetDataHere
- CRowset<TAccessor>.GetDataHere
- CRowset.GetDataHere
- GetDataHere
- CRowset::GetDataHere
- ATL::CRowset::GetDataHere
- ATL::CRowset<TAccessor>::GetDataHere
- ATL.CRowset<TAccessor>.GetDataHere
- ATL.CRowset.GetDataHere
dev_langs:
- C++
helpviewer_keywords:
- GetDataHere method
ms.assetid: 2fe2a987-1c4c-4299-876e-0591caf63af4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7bcef1a5c2b8d5fe360a081c710ba2bd879a713e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetgetdatahere"></a>CRowset::GetDataHere
현재 행의 데이터를 검색 하 고 지정된 된 버퍼에 배치 합니다.  
  
## <a name="syntax"></a>구문  
  
```
HRESULT GetDataHere(int nAccessor,   
  void* pBuffer) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nAccessor`  
 [in] 데이터에 액세스 하기 위해 사용 하는 접근자의 인덱스 번호입니다.  
  
 `pBuffer`  
 [out] 현재 레코드에 대 한 데이터를 넣을 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 함수를 사용 하는 방법의 예제를 보려면는 [MultiRead 샘플](../../visual-cpp-samples.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [CRowset::GetData](../../data/oledb/crowset-getdata.md)