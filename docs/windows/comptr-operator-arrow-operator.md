---
title: "Comptr:: Operator-&gt; 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::operator->
dev_langs: C++
helpviewer_keywords: operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c70c37523132d06bfb04c86cf6f737109da43e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comptroperator-gt-operator"></a>Comptr:: Operator-&gt; 연산자
현재 템플릿 매개 변수에 지정된 형식에 대한 포인터를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## <a name="return-value"></a>반환 값  
 현재 템플릿 형식 이름으로 지정 된 형식에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 도우미 함수 STDMETHOD 매크로 사용 하 여 발생 하는 불필요 한 오버 헤드를 제거 합니다. 이 함수는 IUnknown 형식 대신 가상 개인 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)