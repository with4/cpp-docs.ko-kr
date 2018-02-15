---
title: 'Cdynamicaccessor:: Setblobsizelimit | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
dev_langs:
- C++
helpviewer_keywords:
- SetBlobSizeLimit method
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5cab35d1d68d4e728d2af5f96a6a3c9e33fc5d25
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicaccessorsetblobsizelimit"></a>CDynamicAccessor::SetBlobSizeLimit
최대 BLOB 크기를 바이트 단위로 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      void SetBlobSizeLimit(DBLENGTH nBlobSize);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nBlobSize`  
 BLOB 크기 제한을 지정합니다.  
  
## <a name="remarks"></a>설명  
 최대 BLOB 크기 (바이트) 설정 이 값 보다 큰 열 데이터를 BLOB로 처리 됩니다. 일부 공급자 (2GB) 등의 열에 대 한 매우 큰 크기를 제공 합니다. 이 크기는 열에 대 한 메모리를 할당을 말고 Blob으로 이러한 열을 바인딩할 하려고 일반적으로 합니다. 모든 메모리를 할당할 필요가 해당 방법으로 없지만 잘림의 한 걱정 없이 모든 데이터를 읽을 수 있습니다. 그러나를 강제 적용 하려는 경우도 있습니다. `CDynamicAccessor` 네이티브 데이터 형식으로에 큰 열을 바인딩할 수 있습니다. 이 작업을 수행 하려면 호출 `SetBlobSizeLimit` 호출 하기 전에 **열려**합니다.  
  
 생성자 메서드 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) 최대 BLOB 크기 기본값은 8, 000 바이트를 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)