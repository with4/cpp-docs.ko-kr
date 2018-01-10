---
title: "사용할 접근자 형식 결정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rowsets [C++], data types
- accessors [C++], types
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cb2e18c8b0c5ab110b9818e46e7fc68c08656274
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="determining-which-type-of-accessor-to-use"></a>사용할 접근자 형식 결정
컴파일 시 또는 런타임에 행 집합에서 데이터 형식을 확인할 수 있습니다.  
  
 정적 접근자를 사용 하 여 컴파일 타임에 데이터 형식을 결정 해야 할 경우 (예: `CAccessor`). 수동으로 또는 ATL OLE DB 소비자 마법사를 사용 하 여 데이터 형식을 확인할 수 있습니다.  
  
 런타임 시 데이터 형식을 결정 해야 할 경우 사용 하 여 동적 (`CDynamicAccessor` 또는 해당 자식) 또는 수동 접근자 (`CManualAccessor`). 이러한 경우에 호출할 수 있습니다 `GetColumnInfo` 형식을 결정할 수 있습니다 열 바인딩 정보를 반환 하는 행 집합에 있습니다.  
  
 다음 표에서 소비자 서식 파일에서 제공 하는 접근자의 목록을 표시 합니다. 각 접근자 장점 및 단점에 있습니다. 상황에 따라 하나의 접근자 유형이 요구 사항에 맞게 해야 합니다.  
  
|접근자 클래스|바인딩|매개 변수|주석|  
|--------------------|-------------|---------------|-------------|  
|`CAccessor`|사용자 레코드를 만듭니다 `COLUMN_ENTRY` 매크로입니다. 매크로 접근자에 해당 레코드에서 데이터 멤버를 바인딩합니다. 행 집합을 만들면 열 바인딩을 해제할 수 없습니다.|사용 하 여 예, 한 **param_map이** 매크로 항목입니다. 바인딩되면 매개 변수 바인딩을 해제할 수 없습니다.|가장 빠른 적은 양의 코드 접근자입니다.|  
|`CDynamicAccessor`|자동 번역.|아니요.|행 집합의 데이터 형식을 확인할 수 없는 경우에 유용 합니다.|  
|`CDynamicParameterAccessor`|자동으로 가능 하지만 [재정의](../../data/oledb/overriding-a-dynamic-accessor.md)합니다.|예, 공급자가 지 원하는 경우 `ICommandWithParameters`합니다. 매개 변수는 자동으로 바인딩됩니다.|방식 보다 속도가 느립니다 `CDynamicAccessor` 일반 저장된 프로시저 호출에 유용 합니다.|  
|**CDynamicStringAccessor [A, W]**|자동 번역.|아니요.|문자열 데이터로 데이터 저장소에서 액세스 되는 데이터를 검색 합니다.|  
|`CManualAccessor`|사용 하 여 수동 `AddBindEntry`합니다.|사용 하 여 수동으로 `AddParameterEntry`합니다.|매우 빠릅니다. 매개 변수 및 열 한 번만 바인딩됩니다. 사용할 데이터의 형식을 확인할 수 있습니다. (참조 [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) 예제를 보려면 샘플.) 보다 더 많은 코드가 필요 `CDynamicAccessor` 또는 `CAccessor`합니다. 와 더 비슷하게 OLE DB를 직접 호출 됩니다.|  
|`CXMLAccessor`|자동 번역.|아니요.|문자열 데이터로 데이터 저장소에서 액세스 되는 데이터를 검색 하 고 같이 XML 태그가 지정 된 데이터 형식을 지정 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)