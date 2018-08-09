---
title: 'Asyncbase:: Onclose 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnClose
dev_langs:
- C++
helpviewer_keywords:
- OnClose method
ms.assetid: 96766450-c262-4611-8534-7d190b799142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c1b888b9d3e3f3c80c3aff40f5fd545ece9cca6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650640"
---
# <a name="asyncbaseonclose-method"></a>AsyncBase::OnClose 메서드
파생된 클래스에서 재정의 하는 경우 비동기 작업을 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
virtual void OnClose(  
   void  
) = 0;  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)   
 [AsyncBase::Close 메서드](../windows/asyncbase-close-method.md)