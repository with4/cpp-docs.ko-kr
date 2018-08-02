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
ms.openlocfilehash: fac3a845ea7c512f5a7ccffdabdf67ce26029ff8
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466165"
---
# <a name="comptroperator-operator"></a>ComPtr::operator= 연산자
현재 값을 할당 **ComPtr**합니다.  
  
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
 *U*  
 클래스입니다.  
  
 *other*  
 포인터, 참조 또는 rvalue 참조 형식 또는 다른 **ComPtr**합니다.  
  
## <a name="return-value"></a>반환 값  
 현재에 대 한 참조가 **ComPtr**합니다.  
  
## <a name="remarks"></a>설명  
 이 연산자의 첫 번째 버전은 현재 빈 값을 할당 **ComPtr**합니다.  
  
 두 번째 버전에서는 할당에 대 한 인터페이스 포인터 없는 경우 현재 동일 **ComPtr** 인터페이스 포인터를 두 번째 인터페이스 포인터를 현재 할당 됩니다 **ComPtr**합니다.  
  
 세 번째 버전에서는 할당에 대 한 인터페이스 포인터를 현재 할당 됩니다 **ComPtr**합니다.  
  
 할당 값의 인터페이스 포인터를 현재 경우 네 번째 버전에서는 **ComPtr** 인터페이스 포인터를 두 번째 인터페이스 포인터를 현재 할당 됩니다 **ComPtr**합니다.  
  
 다섯 번째 버전이 복사 연산자입니다. 에 대 한 참조를 **ComPtr** 현재 할당 된 **ComPtr**합니다.  
  
 여섯 번째 버전은 이동 의미 체계;를 사용 하는 복사 연산자 rvalue 참조를 **ComPtr** 캐스팅 하 고 현재 할당 한 다음 모든 형식이 정적 인지 **ComPtr**합니다.  
  
 일곱 번째 버전은 이동 의미 체계;를 사용 하는 복사 연산자 rvalue 참조를 **ComPtr** 형식의 *U* 정적 캐스팅 한 다음 이며 현재 할당 **ComPtr**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)