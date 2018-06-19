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
ms.openlocfilehash: 7b0aef97645d515a03dcf2cab90eedc06f07971c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874147"
---
# <a name="handletinternalclose-method"></a>HandleT::InternalClose 메서드
현재 HandleT 개체를 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```  
virtual bool InternalClose();  
```  
  
## <a name="return-value"></a>반환 값  
 `true` 현재 HandleT 성공적으로 닫힌 경우 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 InternalClose() 보호 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)