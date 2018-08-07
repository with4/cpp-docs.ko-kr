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
ms.openlocfilehash: 654ef60c924a14e861971c651899c8baea0300ef
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462708"
---
# <a name="classfactorylockserver-method"></a>ClassFactory::LockServer 메서드
증가 또는 현재 추적 되는 개체의 기본 수 감소 **ClassFactory** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *떼*  
 **true** 추적 된 개체 수가 증가 합니다. **false** 추적 된 개체 수가 감소 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 E_FAIL입니다.  
  
## <a name="remarks"></a>설명  
 ClassFactory 개체의 기본 인스턴스에서 추적 합니다 [모듈](../windows/module-class.md) 클래스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ClassFactory 클래스](../windows/classfactory-class.md)