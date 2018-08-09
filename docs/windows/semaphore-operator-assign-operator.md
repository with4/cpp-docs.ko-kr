---
title: 'Semaphore:: operator = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: ea19839f-91f0-4b00-a35b-5728fcba4981
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eee563a52a24d2b78157b640ae6e84217c03af64
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651280"
---
# <a name="semaphoreoperator-operator"></a>Semaphore::operator= 연산자
지정 된 핸들을 이동 하는 **세마포** 개체를 현재 **세마포** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Semaphore& operator=(  
   _Inout_ Semaphore&& h  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *h*  
 대 한 Rvalue 참조를 **세마포** 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 현재에 대 한 참조가 **세마포** 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>참고 항목
 [Semaphore 클래스](../windows/semaphore-class.md)