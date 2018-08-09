---
title: GetActivationFactory 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3fe0d03ead29362ea2926f6326557df2ba6a2cd9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649249"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory 함수
템플릿 매개 변수로 지정 된 형식에 대 한 활성화 팩터리를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template<typename T>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 활성화 팩터리 형식을 지정 하는 템플릿 매개 변수입니다.  
  
 *activatableClassId*  
 활성화 팩터리를 생성할 수 있는 클래스의 이름입니다.  
  
 *팩터리*  
 이 작업이 완료 되 면 형식에 대 한 활성화 팩터리에 대 한 참조가 *T*합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 그렇지 않은 경우이 작업이 실패 한 이유를 나타내는 HRESULT 오류가 발생 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **Namespace:** windows:: foundation  
  
## <a name="see-also"></a>참고 항목  
 [Windows::Foundation 네임스페이스](../windows/windows-foundation-namespace.md)