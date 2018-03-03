---
title: "begin 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::begin
dev_langs:
- C++
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d47244e6428979f5319c9ee02f252ef3e559f7ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="begin-function"></a>begin 함수
지정된 인터페이스 매개 변수로 액세스되는 컬렉션 시작 부분을 가리키는 반복자를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
template <typename T>   
    ::Platform::Collections::VectorIterator<T>   
    begin(  
          IVector<T>^ v         );  
  
template <typename T>   
    ::Platform::Collections::VectorViewIterator<T>   
    begin(  
          IVectorView<T>^ v  
         );   
  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    begin(  
          IIterable<T>^ i         );  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 템플릿 형식 매개 변수입니다.  
  
 `v`  
 벡터의 컬렉션인\<T > 또는\<T > IVector에서 액세스할 수 있는 개체\<T > 또는 IVectorView\<T > 인터페이스입니다.  
  
 `i`  
 IIterable에서 액세스할 수 있는 임의 Windows 런타임 개체의 컬렉션\<T > 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 컬렉션의 시작 부분을 가리키는 반복기입니다.  
  
### <a name="remarks"></a>설명  
 처음 두 템플릿 함수는 반복기를 반환하고 세 번째 템플릿 함수는 입력 반복기를 반환합니다.  
  
 개체에서 반환 되는 시작 VectorIterator는 VectorProxy 형식의 요소를 저장 하는 프록시 반복기\<T >. 그러나 프록시 개체는 사용자 코드에 거의 표시되지 않습니다. 자세한 내용은 [컬렉션(C++/CX)](../cppcx/collections-c-cx.md)을 참조하세요.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>참고 항목  
 [Windows::Foundation::Collections Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)