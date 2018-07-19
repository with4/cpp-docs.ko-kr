---
title: HString 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
dev_langs:
- C++
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8544a78fdbdab19f44081853f5f5878f980cec01
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879374"
---
# <a name="hstring-class"></a>HString 클래스
RAII 패턴을 사용 하 여를 HSTRING의 수명을 관리 하기 위한 도우미 클래스입니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
class HString;  
```  
  
## <a name="remarks"></a>설명  
 Windows 런타임 HSTRING 핸들을 통해 문자열에 대 한 액세스를 제공합니다. HString 클래스 편의 함수와 HSTRING 핸들 사용을 간소화 하는 연산자를 제공 합니다. 이 클래스는 RAII 패턴을 통해 소유 HSTRING의 수명을 처리할 수 있습니다. 
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[HString::HString 생성자](../windows/hstring-hstring-constructor.md)|HString 클래스의 새 인스턴스를 초기화합니다.|  
|[HString::~HString 소멸자](../windows/hstring-tilde-hstring-destructor.md)|HString 클래스의 현재 인스턴스를 제거 합니다.|  
  
### <a name="members"></a>멤버  
  
|이름|설명|  
|----------|-----------------|  
|[HString::Set 메서드](../windows/hstring-set-method.md)|지정 된 와이드 문자 문자열 또는 HString 매개 변수를 현재 HString 개체가 값을 설정합니다.|  
|[HString::Attach 메서드](../windows/hstring-attach-method.md)|현재 HString 개체가 지정 된 HString 개체를 연결합니다.|  
|[HString::CopyTo 메서드](../windows/hstring-copyto-method.md)|현재 HString 복사본 개체 HSTRING 개체입니다.|  
|[HString::Detach 메서드](../windows/hstring-detach-method.md)|지정된 된 HString 개체를 기본 값에서 연결을 끊습니다.|  
|[HString::GetAddressOf 메서드](../windows/hstring-getaddressof-method.md)|기본 HSTRING 핸들에 대 한 포인터를 검색합니다.|  
|[HString::Get 메서드](../windows/hstring-get-method.md)|기본 HSTRING 핸들의 값을 검색 합니다.|  
|[HString::Release 메서드](../windows/hstring-release-method.md)|원본 문자열 값을 삭제 하 고 현재 HString 개체가 비어 있는 값을 초기화 합니다.|  
|[HString::MakeReference 메서드](../windows/hstring-makereference-method.md)|지정 된 문자열 매개 변수에서 HStringReference 개체를 만듭니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HString::Operator= 연산자](../windows/hstring-operator-assign-operator.md)|현재 HString 개체가 다른 HString 개체의 값을 이동합니다.|  
|[HString::Operator== 연산자](../windows/hstring-operator-equality-operator.md)|두 개의 매개 변수가 같은지 여부를 나타냅니다.|  
|[HString::Operator!= 연산자](../windows/hstring-operator-inequality-operator.md)|두 개의 매개 변수가 같지 않은지를 나타냅니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `HString`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)