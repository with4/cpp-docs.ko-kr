---
title: default (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.default
dev_langs:
- C++
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6b24b0ed9b8e547a52388b6f93a4955da782331b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="default-c"></a>default(C++)
coclass 내에 정의된 custom 또는 dispinterface가 기본 프로그래밍 인터페이스를 나타낸다는 것을 의미합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ default(  
   interface1,  
   interface2  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *interface1*  
 기본 인터페이스는 **default** 특성으로 정의된 클래스에 따라 개체를 만드는 스크립팅 환경에 사용할 수 있습니다.  
  
 지정된 기본 인터페이스가 없는 경우 처음에 발생하는 비 소스 인터페이스가 기본값으로 사용됩니다.  
  
 *interface2*(선택 사항)  
 기본 소스 인터페이스입니다. 이 인터페이스는 [source](../windows/source-cpp.md) 특성을 사용하여 지정해야 합니다.  
  
 지정된 기본 소스 인터페이스가 없는 경우 첫 번째 소스 인터페이스가 기본값으로 사용됩니다.  
  
## <a name="remarks"></a>설명  
 **default** C++ 특성에는 [default](http://msdn.microsoft.com/library/windows/desktop/aa366787) MIDL 특성과 동일한 기능이 있습니다. **default** 특성을 [case](../windows/case-cpp.md) 특성과 함께 사용할 수도 있습니다.  
  
## <a name="example"></a>예  
 다음 코드에서는 coclass 정의에서 **default** 를 사용하여 **ICustomDispatch** 를 기본 프로그래밍 인터페이스로 지정하는 방법을 보여 줍니다.  
  
```  
// cpp_attr_ref_default.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]   
__interface IDual {  
   HRESULT Dual([in] long l, [out, retval] long *pLong);  
};  
  
[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustomDispatch : public IDispatch {  
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);  
};  
  
[   coclass,  
   default(ICustomDispatch),   
   source(IDual),  
   uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")  
]  
class CClass : public ICustom, public IDual, public ICustomDispatch {  
   HRESULT Custom(long l, long *pLong) { return(S_OK); }  
   HRESULT Dual(long l, long *pLong) { return(S_OK); }  
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }  
};  
  
int main() {  
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch  
   CClass *pClass = new CClass;  
  
   long llong;  
  
   pClass->custom(1, &llong);  
   pClass->dual(1, &llong);  
   pClass->dispinterface(1, &llong);  
   pClass->dispatch(1, &llong);  
  
   delete pClass;  
#endif  
   return(0);  
}  
```  
  
 [source](../windows/source-cpp.md) 특성에는 **default**사용 방법에 대한 예제도 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, `struct`, 데이터 멤버|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass** ( **클래스** 또는 `struct`에 적용된 경우)|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [coclass](../windows/coclass.md)   
