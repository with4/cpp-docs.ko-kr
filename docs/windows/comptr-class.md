---
title: ComPtr 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr class
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 36ecb5fdf292873c18df8f6b2f032865f44bafd2
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="comptr-class"></a>ComPtr 클래스
템플릿 매개 변수로 지정된 인터페이스를 나타내는 *스마트 포인터* 형식을 만듭니다. ComPtr은 기본 인터페이스 포인터의 참조 개수를 자동으로 관리하여 참조 횟수가 0이 되면 인터페이스를 릴리스합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <typename T>  
class ComPtr;  
  
template<class T>  
friend class ComPtr;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 ComPtr이 나타내는 인터페이스입니다.  
  
 `U`  
 현재 ComPtr이 friend인 클래스입니다. 이 매개 변수를 사용하는 템플릿은 보호됩니다.  
  
## <a name="remarks"></a>설명  
 ComPtr<>은 기본 인터페이스 포인터를 나타내는 형식을 선언합니다. ComPtr <>를 사용 하 여 변수를 선언한 다음 화살표 멤버 액세스 연산자를 사용 하 여를 (`->`) 인터페이스 멤버 함수에 액세스 합니다.  
  
 스마트 포인터에 대한 자세한 내용은 MSDN Library에서 [COM Coding Practices](http://msdn.microsoft.com/en-us/76aca556-b4d6-4e67-a2a3-4439900f0c39)항목의 "COM 스마트 포인터" 하위 섹션을 참조하세요.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`InterfaceType`|`T` 템플릿 매개 변수로 지정된 형식의 동의어입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtr::ComPtr 생성자](../windows/comptr-comptr-constructor.md)|ComPtr 클래스의 새 인스턴스를 초기화합니다. 오버로드는 기본, 복사, 이동 및 변환 생성자를 제공합니다.|  
|[ComPtr::~ComPtr 소멸자](../windows/comptr-tilde-comptr-destructor.md)|ComPtr의 인스턴스 초기화를 취소합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtr::As 메서드](../windows/comptr-as-method.md)|지정된 템플릿 매개 변수로 식별된 인터페이스를 나타내는 ComPtr 개체를 반환합니다.|  
|[ComPtr::AsIID 메서드](../windows/comptr-asiid-method.md)|지정된 인터페이스 ID로 식별된 인터페이스를 나타내는 ComPtr 개체를 반환합니다.|  
|[ComPtr::AsWeak 메서드](../windows/comptr-asweak-method.md)|현재 개체에 대한 약한 참조를 검색합니다.|  
|[ComPtr::Attach 메서드](../windows/comptr-attach-method.md)|현재 템플릿 형식 매개 변수에 지정된 인터페이스 형식과 이 ComPtr을 연결합니다.|  
|[ComPtr::CopyTo 메서드](../windows/comptr-copyto-method.md)|이 ComPtr과 연결된 지정된 인터페이스 또는 현재 인터페이스를 지정된 출력 포인터에 복사합니다.|  
|[ComPtr::Detach 메서드](../windows/comptr-detach-method.md)|이 ComPtr이 나타내는 인터페이스에서 이 ComPtr의 연결을 끊습니다.|  
|[ComPtr::Get 메서드](../windows/comptr-get-method.md)|이 ComPtr과 연결된 인터페이스에 대한 포인터를 검색합니다.|  
|[ComPtr::GetAddressOf 메서드](../windows/comptr-getaddressof-method.md)|이 ComPtr이 나타내는 인터페이스에 대한 포인터를 포함하는, [ptr_](../windows/comptr-ptr-data-member.md) 데이터 멤버의 주소를 검색합니다.|  
|[ComPtr::ReleaseAndGetAddressOf 메서드](../windows/comptr-releaseandgetaddressof-method.md)|이 ComPtr과 연결된 인터페이스를 해제한 다음 해제된 인터페이스에 대한 포인터를 포함하는, [ptr_](../windows/comptr-ptr-data-member.md) 데이터 멤버의 주소를 검색합니다.|  
|[ComPtr::Reset](../windows/comptr-reset.md)|이 ComPtr과 연관된 인터페이스의 포인터에 대한 모든 참조를 해제합니다.|  
|[ComPtr::Swap 메서드](../windows/comptr-swap-method.md)|현재 ComPtr에서 관리하는 인터페이스를 지정된 ComPtr에서 관리하는 인터페이스와 교환합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtr::InternalAddRef 메서드](../windows/comptr-internaladdref-method.md)|이 ComPtr과 연결된 인터페이스의 참조 개수를 증가시킵니다.|  
|[ComPtr::InternalRelease 메서드](../windows/comptr-internalrelease-method.md)|이 ComPtr과 연결된 인터페이스에서 COM 해제 작업을 수행합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtr::operator Microsoft::WRL::Details::BoolType 연산자](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|ComPtr이 인터페이스의 개체 수명을 관리하고 있는지 여부를 나타냅니다.|  
|[ComPtr::operator& 연산자](../windows/comptr-operator-ampersand-operator.md)|현재 ComPtr의 주소를 검색합니다.|  
|[ComPtr::operator= 연산자](../windows/comptr-operator-assign-operator.md)|현재 ComPtr에 값을 할당합니다.|  
|[ComPtr::operator-> 연산자](../windows/comptr-operator-arrow-operator.md)|현재 템플릿 매개 변수에 지정된 형식에 대한 포인터를 검색합니다.|  
|[ComPtr::operator== 연산자](../windows/comptr-operator-equality-operator.md)|두 ComPtr 개체가 같은지를 나타냅니다.|  
|[ComPtr::operator!= 연산자](../windows/comptr-operator-inequality-operator.md)|두 ComPtr 개체가 같지 않은지를 나타냅니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtr::ptr_ 데이터 멤버](../windows/comptr-ptr-data-member.md)|이 ComPtr과 연결되어 있고 이 ComPtr에서 관리하는 인터페이스에 대한 포인터를 포함합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ComPtr`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)