---
title: 'Activationfactory:: Queryinterface 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method
ms.assetid: 2a9b71aa-61c0-43f7-aa35-00f0ee0af031
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2a2ed2393f25dac416cf3b6dfd1b178190d368a6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647104"
---
# <a name="activationfactoryqueryinterface-method"></a>ActivationFactory::QueryInterface 메서드
지정된 된 인터페이스에 대 한 포인터를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDMETHOD(  
   QueryInterface  
)(REFIID riid, _Deref_out_ void **ppvObject);  
```  
  
### <a name="parameters"></a>매개 변수  
 *riid*  
 인터페이스 ID입니다.  
  
 *ppvObject*  
 이 작업이 완료 되 면, 매개 변수에서 지정 된 인터페이스에 대 한 포인터 *riid*합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ActivationFactory 클래스](../windows/activationfactory-class.md)