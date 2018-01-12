---
title: 'Cdynamicaccessor:: Setblobhandling | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
dev_langs: C++
helpviewer_keywords: SetBlobHandling method
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 02b9be4b187f55d9bfb8f3ee5e572f682742f538
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessorsetblobhandling"></a>CDynamicAccessor::SetBlobHandling
현재 행에 대 한 값을 처리 하는 BLOB를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      bool SetBlobHandling(  
   DBBLOBHANDLINGENUM eBlobHandling   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `eBlobHandling`  
 BLOB 데이터의 처리 방법을 지정 합니다. 다음 값을 사용할 수 있습니다.  
  
-   **DBBLOBHANDLING_DEFAULT**: 보다 큰 열 데이터를 처리 `nBlobSize` (의해 설정 `SetBlobSizeLimit`)로 BLOB 데이터과 통해 검색 한 `ISequentialStream` 또는 `IStream` 개체입니다. 이 옵션 보다 더 큰 데이터를 포함 하는 모든 열을 바인딩할 하겠습니다 `nBlobSize` 으로 나열 또는 **DBTYPE_IUNKNOWN** BLOB 데이터로 합니다.  
  
-   **DBBLOBHANDLING_NOSTREAMS**: 보다 큰 열 데이터 처리 `nBlobSize` (의해 설정 `SetBlobSizeLimit`)로 BLOB 데이터과 공급자 할당, 소비자가 소유한 메모리에 대 한 참조를 통해 검색 합니다. 이 옵션은 둘 이상의 BLOB 열이 있는 테이블에 대 한 유용 하 고 공급자가 지 원하는 하나만 `ISequentialStream` 접근자 당 개체입니다.  
  
-   **DBBLOBHANDLING_SKIP**: 건너뛰기 (연결 하지 않음) Blob을 포함 한 것으로 한정 되는 열 (접근자 바인딩하거나 열 값을 검색 하지 것입니다 하지만 열 상태 및 길이 응용 프로그램은 여전히 검색).  
  
## <a name="remarks"></a>설명  
 호출 해야 `SetBlobHandling` 호출 하기 전에 **열려**합니다.  
  
 생성자 메서드 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) 설정 하는 값을 처리 하는 BLOB **DBBLOBHANDLING_DEFAULT**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)