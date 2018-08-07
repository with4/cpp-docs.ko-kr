---
title: 'Dontusenewusemake:: Operator 새 연산자 | Microsoft Docs'
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
ms.openlocfilehash: 59354062dded7792dca1cd84683bba64f6a64aa0
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571427"
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
 *__unnamed0*  
 할당할 메모리의 바이트 수를 지정 하는 명명 되지 않은 매개 변수입니다.  
  
 *배치*  
 할당할 형식입니다.  
  
## <a name="return-value"></a>반환 값  
 연산자를 오버 로드 하는 경우 추가 인수를 전달 하는 방법을 제공 **새**합니다.  
  
## <a name="remarks"></a>설명  
 연산자 오버 로드 **새** 에서 사용 되지 않도록 방지 하 고 `RuntimeClass`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [DontUseNewUseMake 클래스](../windows/dontusenewusemake-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)