---
title: 'Comptr:: Operator! = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator!=
dev_langs:
- C++
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 91b1bb70450cac677abcc886ab2eb911280f86dd
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642094"
---
# <a name="comptroperator-operator"></a>ComPtr::operator!= 연산자
나타냅니다 두 **ComPtr** 개체가 같지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *a*  
 에 대 한 참조를 **ComPtr** 개체입니다.  
  
 *b*  
 다른에 대 한 참조가 **ComPtr** 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 첫 번째 연산자 생성 **true** 하는 경우 개체 *는* 개체와 같지 않은 *b*고, 그렇지 않으면 **false**합니다.  
  
 두 번째 및 세 번째 연산자를 생성 **true** 경우 개체 *는* 같지 **nullptr**고, 그렇지 않으면 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft:: wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr 클래스](../windows/comptr-class.md)