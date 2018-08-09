---
title: 'Weakreference:: Resolve 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::Resolve
dev_langs:
- C++
helpviewer_keywords:
- Resolve method
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe78f8644768563507f98157ac859993776d7fe9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646204"
---
# <a name="weakreferenceresolve-method"></a>WeakReference::Resolve 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(Resolve)  
   (REFIID riid,   
   _Deref_out_opt_ IInspectable **ppvObject  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *riid*  
 인터페이스 ID입니다.  
  
 *ppvObject*  
 이 작업이 완료 될 때 강력한 참조 횟수가 0이 아닌 경우 현재 강력한 참조의 복사본입니다.  
  
## <a name="return-value"></a>반환 값  
  
-   이 작업에 성공 하면 S_OK와 강력한 참조 횟수는 0입니다. 합니다 *ppvObject* 매개 변수는 설정 **nullptr**합니다.  
  
-   이 작업은 성공 하 고 강력한 참조 횟수가 0이 아닌 경우 S_OK입니다. 합니다 *ppvObject* 매개 변수는 강력한 참조를 설정 합니다.  
  
-   그렇지 않은 경우 이유를 나타내는 HRESULT이이 작업이 실패 했습니다.  
  
## <a name="remarks"></a>설명  
 강력한 참조 횟수가 0이 아닌 경우 현재 강력한 참조 값으로 지정된 된 포인터를 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [WeakReference 클래스 1](../windows/weakreference-class1.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)