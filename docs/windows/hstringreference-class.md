---
title: "HStringReference 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference
dev_langs: C++
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97900bd44dfdcede187b20b181c64d235eac60fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hstringreference-class"></a>HStringReference 클래스
기존 문자열에서 만든 HSTRING를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
class HStringReference;  
```  
  
## <a name="remarks"></a>설명  
 새 HSTRING에서 백업 버퍼의 수명은 Windows 런타임에서 관리 되지 않습니다. 호출자는 소스 문자열 힙 할당을 방지 하 고 메모리 누수 위험 제거 하려면 스택 프레임에 할당 합니다. 또한 호출자는 소스 문자열은 연결 된 HSTRING의 수명 동안 변경 되지 않은 확인 해야 합니다. 자세한 내용은 참조 [WindowsCreateStringReference 함수](http://msdn.microsoft.com/en-us/0361bb7e-da49-4289-a93e-de7aab8712ac)합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[HStringReference::HStringReference 생성자](../windows/hstringreference-hstringreference-constructor.md)|HStringReference 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|[HStringReference::CopyTo 메서드](../windows/hstringreference-copyto-method.md)|복사본은 현재 HStringReference 개체 HSTRING 개체입니다.|  
|[HStringReference::Get 메서드](../windows/hstringreference-get-method.md)|기본 HSTRING 핸들의 값을 검색 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HStringReference::Operator= 연산자](../windows/hstringreference-operator-assign-operator.md)|다른 HStringReference 개체의 값은 현재 HStringReference 개체를 이동합니다.|  
|[HStringReference::Operator== 연산자](../windows/hstringreference-operator-equality-operator.md)|두 개의 매개 변수가 같은지 여부를 나타냅니다.|  
|[HStringReference::Operator!= 연산자](../windows/hstringreference-operator-inequality-operator.md)|두 개의 매개 변수가 같지 않은지를 나타냅니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `HStringReference`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)