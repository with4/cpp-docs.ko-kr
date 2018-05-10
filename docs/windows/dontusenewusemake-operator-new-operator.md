---
title: 'Dontusenewusemake:: Operator new 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs:
- C++
helpviewer_keywords:
- operator new operator
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9785ea27c79ff0a118ff3697a22804c520b265ee
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="dontusenewusemakeoperator-new-operator"></a>DontUseNewUseMake::operator 새 연산자
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
void* operator new(  
   size_t,  
   _In_ void* placement  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `__unnamed0`  
 할당할 메모리의 바이트 수를 지정 하는 명명 되지 않은 매개 변수입니다.  
  
 `placement`  
 에 할당할 형식입니다.  
  
## <a name="return-value"></a>반환 값  
 연산자를 오버 로드 하는 경우 추가 인수를 전달 하는 방법을 제공 `new`합니다.  
  
## <a name="remarks"></a>설명  
 연산자 오버 로드 `new` RuntimeClass에서 사용 되지 않도록 방지 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [DontUseNewUseMake 클래스](../windows/dontusenewusemake-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)