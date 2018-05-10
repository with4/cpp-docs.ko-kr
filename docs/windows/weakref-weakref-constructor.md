---
title: 'Weakref:: Weakref 생성자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef, constructor
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ae70dabdd86fedf82c26c0c7d9a09d842e2310e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="weakrefweakref-constructor"></a>WeakRef::WeakRef 생성자
WeakRef 클래스의 새 인스턴스를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
WeakRef();  
WeakRef(  
   decltype(__nullptr)  
);  
  
WeakRef(  
   _In_opt_ IWeakReference* ptr  
);  
  
WeakRef(  
   const ComPtr<IWeakReference>& ptr  
);  
  
WeakRef(  
   const WeakRef& ptr  
);  
  
WeakRef(  
   _Inout_ WeakRef&& ptr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ptr`  
 포인터, 참조 또는 rvalue 참조 현재 WeakRef 개체를 초기화 하는 기존 개체에 있습니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 생성자는 빈 WeakRef 개체를 초기화합니다. 두 번째 생성자는 IWeakReference 인터페이스에 대 한 포인터에서 WeakRef 개체를 초기화합니다. 세 번째 생성자는 ComPtr에 대 한 참조에서 WeakRef 개체를 초기화 합니다.\<IWeakReference > 개체입니다. 네 번째와 다섯 번째 생성자는 다른 WeakRef 개체에서 WeakRef 개체를 초기화 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)