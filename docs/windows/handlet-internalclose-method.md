---
title: "Handlet:: Internalclose 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
dev_langs:
- C++
helpviewer_keywords:
- InternalClose method
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c91d3a6eb2c03b70ca50b28189e4ab4530a2e3bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="handletinternalclose-method"></a>HandleT::InternalClose 메서드
현재 HandleT 개체를 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```  
virtual bool InternalClose();  
```  
  
## <a name="return-value"></a>반환 값  
 `true`현재 HandleT 성공적으로 닫힌 경우 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 InternalClose() 보호 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)