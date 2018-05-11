---
title: WeakRef 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef class
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ba7efc595be55b807cd3f044269db0debcb72407
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="weakref-class"></a>WeakRef 클래스
클래식 COM이 아닌 Windows 런타임에서만 사용할 수 있는 *약한 참조* 를 나타냅니다. 약한 참조는 액세스할 수 있거나 액세스할 수 없는 개체를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class WeakRef : public ComPtr<IWeakReference>  
```  
  
## <a name="remarks"></a>설명  
 WeakRef 개체는 개체와 연결된 *강력한 참조*를 유지 관리하며, 유효할 수도 있고 유효하지 않을 수도 있습니다. As() 또는 AsIID() 메서드를 호출하여 강력한 참조를 가져옵니다. 강력한 참조가 유효한 경우 연결된 개체에 액세스할 수 있습니다. 강력한 참조가 올바르지 않은 경우(`nullptr`) 연결된 개체에 액세스할 수 없습니다.  
  
 WeakRef 개체는 일반적으로 외부 스레드나 응용 프로그램에 의해 그 존재가 제어되는 개체를 나타내는 데 사용됩니다. 예를 들어 파일 개체에 대한 참조에서 WeakRef 개체를 생성합니다. 파일이 열려 있는 동안 강력한 참조는 유효합니다. 그러나 파일이 닫히면 강력한 참조는 유효하지 않게 됩니다.  
  
 Windows 10 SDK에서는 [As](../windows/weakref-as-method.md), [AsIID](../windows/weakref-asiid-method.md) 및 [CopyTo](../windows/weakref-copyto-method.md) 메서드의 동작 변경이 있습니다. 이전에는 이러한 메서드를 호출한 후 강력한 참조를 성공적으로 가져왔는지 확인하기 위해 다음 코드처럼 WeakRef에서 `nullptr` 을 검사할 수 있었습니다.  
  
```cpp  
WeakRef wr;  
strongComptrRef.AsWeak(&wr);  
  
// Now suppose that the object strongComPtrRef points to no longer exists  
// and the following code tries to get a strong ref from the weak ref:  
ComPtr<ISomeInterface> strongRef;  
HRESULT hr = wr.As(&strongRef);  
  
// This check won't work with the Windows 10 SDK version of the library.  
// Check the input pointer instead.  
if(wr == nullptr)  
{  
    wprintf(L"Couldn’t get strong ref!");  
}  
  
```  
  
 위의 코드는 Windows 10 SDK(이상)를 사용하는 경우 작동하지 않습니다. 대신에 전달 된 포인터를 검사 `nullptr`합니다.  
  
```cpp  
if (strongRef == nullptr)  
{  
    wprintf(L"Couldn't get strong ref!");  
 }  
  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[WeakRef::WeakRef 생성자](../windows/weakref-weakref-constructor.md)|WeakRef 클래스의 새 인스턴스를 초기화합니다.|  
|[WeakRef::~WeakRef 소멸자](../windows/weakref-tilde-weakref-destructor.md)|WeakRef 클래스의 현재 인스턴스 초기화를 취소합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[WeakRef::As 메서드](../windows/weakref-as-method.md)|지정된 인터페이스를 나타내도록 지정된 ComPtr 포인터 매개 변수를 설정합니다.|  
|[WeakRef::AsIID 메서드](../windows/weakref-asiid-method.md)|지정된 인터페이스 ID를 나타내도록 지정된 ComPtr 포인터 매개 변수를 설정합니다.|  
|[WeakRef::CopyTo 메서드](../windows/weakref-copyto-method.md)|사용 가능한 경우 지정된 포인터 변수에 인터페이스에 대한 포인터를 할당합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[WeakRef::operator& 연산자](../windows/weakref-operator-ampersand-operator.md)|현재 WeakRef 개체를 나타내는 ComPtrRef 개체를 반환합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ComPtr`  
  
 `WeakRef`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)