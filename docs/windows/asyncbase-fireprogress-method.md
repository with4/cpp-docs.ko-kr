---
title: 'Asyncbase:: Fireprogress 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireProgress
dev_langs:
- C++
helpviewer_keywords:
- FireProgress method
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: faa2e1af556f0184fa88055bcbf154eb783e24e5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463599"
---
# <a name="asyncbasefireprogress-method"></a>AsyncBase::FireProgress 메서드
현재 진행률 이벤트 처리기를 호출합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void FireProgress(  
   const typename ProgressTraits::Arg2Type arg  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *arg*  
 이벤트 처리기 메서드를 호출 합니다.  
  
## <a name="remarks"></a>설명  
 `ProgressTraits` 파생 됩니다 [ArgTraitsHelper 구조체](../windows/argtraitshelper-structure.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)