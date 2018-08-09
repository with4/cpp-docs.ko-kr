---
title: 'Handlet:: Internalclose 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
dev_langs:
- C++
helpviewer_keywords:
- InternalClose method
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2190a8e85f81062cc1167aa844fccf4afc819bc9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648804"
---
# <a name="handletinternalclose-method"></a>HandleT::InternalClose 메서드
현재 닫습니다 **HandleT** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
virtual bool InternalClose();  
```  
  
## <a name="return-value"></a>반환 값  
 **true** 하는 경우 현재 **HandleT** 이 고, 그렇지 않으면 닫은 **false**합니다.  
  
## <a name="remarks"></a>설명  
 **InternalClose()** 됩니다 **보호**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)