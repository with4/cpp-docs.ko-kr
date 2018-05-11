---
title: 'Classfactory:: Lockserver 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- LockServer method
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e09a795688c7e2b31771126f9e4036ddfbd8e4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="classfactorylockserver-method"></a>ClassFactory::LockServer 메서드
현재 ClassFactory 개체에서 추적하는 기본 개체 수를 늘리거나 줄입니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fLock`  
 추적된 개체 수를 늘리려면 `true`입니다. 추적된 개체 수를 줄이려면 `false`입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 E_FAIL입니다.  
  
## <a name="remarks"></a>설명  
 ClassFactory 개체의 기본 인스턴스에서는 추적 된 [모듈](../windows/module-class.md) 클래스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ClassFactory 클래스](../windows/classfactory-class.md)