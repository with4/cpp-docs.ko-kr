---
title: 단순한 읽기 전용 공급자 기능 향상 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c88714e4e1651839cdc5fd4b92d3c5222aa08d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="enhancing-the-simple-read-only-provider"></a>단순한 읽기 전용 공급자의 기능 향상
이 섹션에서는 향상 하는 방법을 보여 줍니다.는 [단순한 읽기 전용 공급자](../../data/oledb/implementing-the-simple-read-only-provider.md) 이전 섹션에서 만든 합니다. `IRowsetLocateImpl` 에 대 한 구현을 만듭니다는 `IRowsetLocate` 인터페이스 및 책갈피 지원을 추가 합니다.  
  
 작업 공급자를 사용 하는 경우에 트랜잭션을 처리 하거나 행 인출 알고리즘의 성능을 향상 시킬 공급자 업데이트를 수행 하려면이 함수는 것이 좋습니다. 공급자 향상 된 기능을 대부분 기존 COM 개체에 인터페이스 추가 작업이 포함 됩니다.  
  
 다음 항목의 예제를 추가 하 여 행을 인출 하는 메커니즘을 향상 시킵니다.는 `IRowsetLocate` 인터페이스 `CAgentRowset`합니다. 표시 하는 항목에:  
  
-   [RMyProviderRowset IRowsetLocate에서 상속 하는 확인](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md)합니다.  
  
-   [소비자에 게 반환 되는 열을 동적으로 결정](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [단순한 읽기 전용 공급자 만들기](../../data/oledb/creating-a-simple-read-only-provider.md)