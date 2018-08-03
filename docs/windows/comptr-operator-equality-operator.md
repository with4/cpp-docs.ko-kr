---
title: 'Comptr:: Operator = = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator==
dev_langs:
- C++
ms.assetid: 6a26e936-29d4-4b7d-b44a-7c575ad07509
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9750f0d49f4c7a580b2c99d0c833c5381ba20997
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467341"
---
# <a name="comptroperator-operator"></a>ComPtr::operator== 연산자
나타냅니다 두 **ComPtr** 개체는 동일 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
bool operator==(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator==(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *a*  
 에 대 한 참조를 **ComPtr** 개체입니다.  
  
 *b*  
 다른에 대 한 참조가 **ComPtr** 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 첫 번째 연산자 생성 **true** 하는 경우 개체 *는* 개체와 동일한 지 *b*고, 그렇지 않으면 **false**합니다.  
  
 두 번째와 세 번째 연산자에서 생성 **true** 하는 경우 개체 *는* 값과 같음 **nullptr**고, 그렇지 않으면 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft:: wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr 클래스](../windows/comptr-class.md)