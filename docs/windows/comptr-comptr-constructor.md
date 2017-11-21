---
title: "Comptr:: Comptr 생성자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::ComPtr
dev_langs: C++
helpviewer_keywords: ComPtr, constructor
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b31fdcbad35bc65b2d8ca26ccab69e875c1d3aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrcomptr-constructor"></a>ComPtr::ComPtr 생성자
ComPtr 클래스의 새 인스턴스를 초기화합니다. 오버로드는 기본, 복사, 이동 및 변환 생성자를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr<U>&& other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `U`  
 `other` 매개 변수의 형식입니다.  
  
 `other`  
 `U` 형식의 개체입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 첫 번째 생성자는 기본 생성자를 어떤 변환이 가능한 빈 개체를 만듭니다. 두 번째 생성자는 지정 [__nullptr](../windows/nullptr-cpp-component-extensions.md), 빈 개체를 명시적으로 만듭니다.  
  
 세 번째 생성자는 포인터에 의해 지정 된 개체에서 개체를 만듭니다.  
  
 네 번째와 다섯 번째 생성자는 복사 생성자입니다. 현재 형식으로 변환할 경우 다섯 번째 생성자는 개체를 복사 합니다.  
  
 여섯 번째와 일곱 번째 생성자는 이동 생성자입니다. 현재 형식으로 변환할 경우 일곱 번째 생성자는 개체를 이동 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)