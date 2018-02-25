---
title: 'Cdynamicaccessor:: Cdynamicaccessor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicAccessor::CDynamicAccessor
- ATL::CDynamicAccessor::CDynamicAccessor
- ATL.CDynamicAccessor.CDynamicAccessor
- CDynamicAccessor.CDynamicAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicAccessor class, constructor
ms.assetid: bf40fe81-2c85-473e-9075-51ad9b060b39
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4d660b3e7fa537e7abd3ea2b713e5b4f7a0ce798
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorcdynamicaccessor"></a>CDynamicAccessor::CDynamicAccessor
인스턴스화하고 초기화는 `CDynamicAccessor` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      CDynamicAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `eBlobHandling`  
 이진 대형 개체 (BLOB) 데이터의 처리 방법을 지정 합니다. 기본값은 **DBBLOBHANDLING_DEFAULT**합니다. 참조 [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) 에 대 한 설명은 **DBBLOBHANDLINGENUM** 값입니다.  
  
 `nBlobSize`  
 최대 BLOB 크기 (바이트) 이 값에 대 한 열 데이터를 BLOB로 처리 됩니다. 기본값은 8000입니다. 참조 [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) 대 한 자세한 내용은 합니다.  
  
## <a name="remarks"></a>설명  
 초기화 하는 생성자를 사용 하는 경우는 `CDynamicAccessor` 개체 Blob 바인딩합니다 방법을 지정할 수 있습니다. Blob은 그래픽, 사운드 또는 컴파일된 코드와 같은 이진 데이터를 포함할 수 있습니다. 기본 동작은 Blob으로 8, 000 바이트 보다 큰 열을 처리 하 고 바인딩하고 하려고 하는 `ISequentialStream` 개체입니다. 그러나 BLOB 크기를 다른 값을 지정할 수 있습니다.  
  
 지정할 수도 있습니다 방법을 `CDynamicAccessor` BLOB 데이터를 정규화 하는 열 데이터를 처리: 기본 방식으로 BLOB 데이터를 처리할 수 있습니다; 건너뛸 수 있습니다 (연결 하지 않는) 이거나 BLOB 데이터 공급자가 할당 한 메모리의 BLOB 데이터에 바인딩할 수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)