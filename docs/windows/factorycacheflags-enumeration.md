---
title: "FactoryCacheFlags 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::FactoryCacheFlags
dev_langs: C++
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 41b31ccede1cca717418c9f489ab7de67d313319
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags 열거형
팩터리 개체를 캐시하는지 여부를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>설명  
 기본적으로 팩터리 캐싱 정책은로 지정 된 [ModuleType](../windows/moduletype-enumeration.md) 만들 때 템플릿 매개 변수는 [모듈](../windows/module-class.md) 개체입니다. 이 정책을 재정의하려면 팩터리 개체를 만들 때 `FactoryCacheFlags` 값을 지정합니다.  
  
|||  
|-|-|  
|`FactoryCacheDefault`|`Module` 개체의 캐싱 정책이 사용됩니다.|  
|`FactoryCacheEnabled`|`ModuleType` 개체를 만드는 데 사용된 `Module` 템플릿 매개 변수에 관계없이 팩터리 캐싱을 사용합니다.|  
|`FactoryCacheDisabled`|`ModuleType` 개체를 만드는 데 사용된 `Module` 템플릿 매개 변수에 관계없이 팩터리 캐싱을 사용하지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)