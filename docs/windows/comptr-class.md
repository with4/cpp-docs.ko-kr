---
title: ComPtr 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr class
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7e4866df2d948d02a53b2532b0832f161d07ff8c
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647562"
---
# <a name="comptr-class"></a>ComPtr 클래스
템플릿 매개 변수로 지정된 인터페이스를 나타내는 *스마트 포인터* 형식을 만듭니다. **ComPtr** 자동으로 기본 인터페이스 포인터에 대 한 참조 횟수를 유지 관리 하 고 참조 횟수가 0이 되 면 인터페이스를 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <typename T>  
class ComPtr;  
  
template<class T>  
friend class ComPtr;  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 인터페이스는 합니다 **ComPtr** 나타냅니다.  
  
 *U*  
 클래스를 현재 **ComPtr** 이 friend입니다. 이 매개 변수를 사용하는 템플릿은 보호됩니다.  
  
## <a name="remarks"></a>설명  
 `ComPtr<>` 기본 인터페이스 포인터를 나타내는 형식을 선언 합니다. 사용 하 여 `ComPtr<>` 변수를 선언 하 고 다음 화살표 멤버 액세스 연산자를 사용 (`->`) 인터페이스 멤버 함수에 액세스할 수 있습니다.  
  
 스마트 포인터에 대 한 자세한 내용은 "COM 스마트 포인터" 하위 섹션을 참조 합니다 [COM Coding Practices](http://msdn.microsoft.com/76aca556-b4d6-4e67-a2a3-4439900f0c39)MSDN 라이브러리의 항목입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`InterfaceType`|지정 된 형식에 대 한 동의어는 *T* 템플릿 매개 변수입니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtr::ComPtr 생성자](../windows/comptr-comptr-constructor.md)|새 인스턴스를 초기화 합니다 **ComPtr** 클래스입니다. 오버로드는 기본, 복사, 이동 및 변환 생성자를 제공합니다.|  
|[ComPtr::~ComPtr 소멸자](../windows/comptr-tilde-comptr-destructor.md)|인스턴스를 초기화 취소 **ComPtr**합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtr::As 메서드](../windows/comptr-as-method.md)|반환 된 **ComPtr** 지정 된 템플릿 매개 변수로 식별 된 인터페이스를 나타내는 개체입니다.|  
|[ComPtr::AsIID 메서드](../windows/comptr-asiid-method.md)|반환 된 **ComPtr** 지정 된 인터페이스 ID로 식별 된 인터페이스를 나타내는 개체|  
|[ComPtr::AsWeak 메서드](../windows/comptr-asweak-method.md)|현재 개체에 대한 약한 참조를 검색합니다.|  
|[ComPtr::Attach 메서드](../windows/comptr-attach-method.md)|이 연결 **ComPtr** 현재 템플릿 형식 매개 변수에 의해 지정 된 인터페이스 형식을 사용 하 여 합니다.|  
|[ComPtr::CopyTo 메서드](../windows/comptr-copyto-method.md)|현재 또는 지정 된 인터페이스와 관련 된 복사 **ComPtr** 지정 된 출력 포인터에 대 한 합니다.|  
|[ComPtr::Detach 메서드](../windows/comptr-detach-method.md)|이 연결을 끊습니다 **ComPtr** 나타내는 인터페이스입니다.|  
|[ComPtr::Get 메서드](../windows/comptr-get-method.md)|이 사용 하 여 연결 된 인터페이스에 대 한 포인터를 검색 **ComPtr**합니다.|  
|[ComPtr::GetAddressOf 메서드](../windows/comptr-getaddressof-method.md)|주소를 검색 합니다 [ptr_](../windows/comptr-ptr-data-member.md) 이 나타내는 인터페이스에 대 한 포인터를 포함 하는 데이터 멤버 **ComPtr**합니다.|  
|[ComPtr::ReleaseAndGetAddressOf 메서드](../windows/comptr-releaseandgetaddressof-method.md)|와 연결 된 인터페이스를 해제 **ComPtr** 다음의 주소를 검색 합니다 [ptr_](../windows/comptr-ptr-data-member.md) 출시 된 인터페이스에 대 한 포인터를 포함 하는 데이터 멤버입니다.|  
|[ComPtr::Reset](../windows/comptr-reset.md)|이 사용 하 여 연결 된 인터페이스 포인터에 대 한 모든 참조를 해제 **ComPtr**합니다.|  
|[ComPtr::Swap 메서드](../windows/comptr-swap-method.md)|현재 관리 되는 인터페이스를 교환 **ComPtr** 지정 된 관리 인터페이스를 사용 하 여 **ComPtr**합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtr::InternalAddRef 메서드](../windows/comptr-internaladdref-method.md)|와 연결 된 인터페이스의 참조 횟수를 증가 시킵니다 **ComPtr**합니다.|  
|[ComPtr::InternalRelease 메서드](../windows/comptr-internalrelease-method.md)|연결 된이 인터페이스에서 COM 릴리스 작업을 수행 **ComPtr**합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[ComPtr::operator Microsoft::WRL::Details::BoolType 연산자](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|나타냅니다 여부는 **ComPtr** 인터페이스의 개체 수명을 관리 합니다.|  
|[ComPtr::operator& 연산자](../windows/comptr-operator-ampersand-operator.md)|현재 주소를 검색 **ComPtr**합니다.|  
|[ComPtr::operator= 연산자](../windows/comptr-operator-assign-operator.md)|현재 값을 할당 **ComPtr**합니다.|  
|[ComPtr::operator-> 연산자](../windows/comptr-operator-arrow-operator.md)|현재 템플릿 매개 변수에 지정된 형식에 대한 포인터를 검색합니다.|  
|[ComPtr::operator== 연산자](../windows/comptr-operator-equality-operator.md)|나타냅니다 두 **ComPtr** 개체는 동일 합니다.|  
|[ComPtr::operator!= 연산자](../windows/comptr-operator-inequality-operator.md)|나타냅니다 두 **ComPtr** 개체가 같지 않습니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[ComPtr::ptr_ 데이터 멤버](../windows/comptr-ptr-data-member.md)|연결 되 고이 관리 되는 인터페이스에 대 한 포인터를 포함 **ComPtr**합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ComPtr`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)