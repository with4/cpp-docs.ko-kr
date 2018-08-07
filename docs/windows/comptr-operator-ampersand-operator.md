---
title: 'Comptr:: Operator&amp; 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0afff1699a4c7a3a14f07967cfb5ba5727ba0320
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461564"
---
# <a name="comptroperatoramp-operator"></a>Comptr:: Operator&amp; 연산자
와 연결 된 인터페이스를 해제 **ComPtr** 개체를 다음의 주소를 검색 합니다 **ComPtr** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## <a name="return-value"></a>반환 값  
 약한 참조를 현재 **ComPtr**합니다.  
  
## <a name="remarks"></a>설명  
 이 방법은에서 다릅니다 [comptr:: Getaddressof](../windows/comptr-getaddressof-method.md) 는이 메서드는 인터페이스 포인터에 대 한 참조를 해제 합니다. 사용 하 여 `ComPtr::GetAddressOf` 인터페이스 포인터의 주소가 필요 하지만 해당 인터페이스를 해제 하지 않으려는 경우.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)