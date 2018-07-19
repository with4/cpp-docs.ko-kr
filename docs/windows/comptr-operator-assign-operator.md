---
title: 'Comptr:: Operator = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f4066db37de8a993802970784f09141352fef028
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871203"
---
# <a name="comptroperator-operator"></a>ComPtr::operator= 연산자
현재 ComPtr에 값을 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <typename U>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `U`  
 클래스입니다.  
  
 `other`  
 형식 또는 다른 ComPtr 포인터, 참조 또는 rvalue 참조입니다.  
  
## <a name="return-value"></a>반환 값  
 현재 ComPtr에 대 한 참조입니다.  
  
## <a name="remarks"></a>설명  
 이 연산자의 첫 번째 버전은 현재 ComPtr에 빈 값을 할당합니다.  
  
 두 번째 버전에서 할당 된 인터페이스 포인터 현재 ComPtr 인터페이스 포인터와 동일 하 게 없는 경우 현재 ComPtr에 두 번째 인터페이스 포인터 할당 됩니다.  
  
 세 번째 버전에서 할당 된 인터페이스 포인터 현재 ComPtr에 할당 됩니다.  
  
 네 번째 버전에서 인터페이스 포인터 할당 값의 현재 ComPtr 인터페이스 포인터와 동일 하 게 없는 경우 현재 ComPtr에 두 번째 인터페이스 포인터 할당 됩니다.  
  
 5 번째 버전은 복사 연산자. ComPtr에 대 한 참조는 현재 ComPtr에 할당 됩니다.  
  
 여섯 번째 버전은 이동 의미 체계;를 사용 하 여 복사 연산자 ComPtr 캐스팅 한 다음 현재 ComPtr에 할당 된 모든 형식을 정적인 경우에 rvalue 참조입니다.  
  
 일곱 번째 버전은 이동 의미 체계;를 사용 하 여 복사 연산자 형식의 ComPtr에 대 한 rvalue 참조 `U` 정적 캐스팅 한 다음 이며 현재 ComPtr에 할당 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)