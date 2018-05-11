---
title: BLOB_ENTRY_LENGTH | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BLOB_ENTRY_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- BLOB_ENTRY_LENGTH macro
ms.assetid: 832d21ab-5fdd-49ad-af6e-4fca5722ec93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5f76f88d319f0fe06cd109af2095cfe0a4bb7204
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="blobentrylength"></a>BLOB_ENTRY_LENGTH
함께 사용할 `BEGIN_COLUMN_MAP` 및 `END_COLUMN_MAP` binary large object 바인딩할 ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). 비슷한 [BLOB_ENTRY](../../data/oledb/blob-entry.md)제외 하 고이 매크로 BLOB 열의 바이트 길이 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nOrdinal`  
 [in] 열 번호입니다.  
  
 *IID*  
 [in] GUID와 같은 인터페이스 **IDD_ISequentialStream**, BLOB를 검색 하는 데 사용 합니다.  
  
 `flags`  
 [in] OLE 구조적 저장소 모델에 정의 된 대로 플래그 지정 하는 저장소 모드 (예를 들어 **STGM_READ**).  
  
 `data`  
 [in] 사용자 레코드에서 해당 데이터 멤버입니다.  
  
 *length*  
 [out] BLOB 열의 (실제) 길이 (바이트)에서입니다.  
  
## <a name="example"></a>예제  
 참조 [BLOB을 검색 하는 방법을?](../../data/oledb/retrieving-a-blob.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)   
 [BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)