---
title: 'Comptr:: As 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::As
dev_langs:
- C++
helpviewer_keywords:
- As method
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e8307411994fb2f850a71e91b63b44052cca40e0
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461012"
---
# <a name="comptras-method"></a>ComPtr::As 메서드
반환 된 **ComPtr** 지정 된 템플릿 매개 변수로 식별 된 인터페이스를 나타내는 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> p  
) const;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *U*  
 인터페이스를 매개 변수로 표시할 *p*합니다.  
  
 *p*  
 A **ComPtr** 매개 변수에 의해 지정 된 인터페이스를 나타내는 개체입니다 *U*합니다. 매개 변수 *p* 현재 참조 하지 않아야 **ComPtr** 개체입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 템플릿은 [자동](../cpp/auto-cpp.md) 형식 추론 키워드와 같은 C++ 언어 기능을 지원하는 내부 도우미 특수화입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)