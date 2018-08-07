---
title: 'Comptr:: Swap 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::Swap
dev_langs:
- C++
helpviewer_keywords:
- Swap method
ms.assetid: 74275f00-b24e-4b4c-b8b6-ac2aa2dd7ae9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fff9e812a6946dd15de5b2d33f57358d02246dab
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462481"
---
# <a name="comptrswap-method"></a>ComPtr::Swap 메서드
현재 관리 되는 인터페이스를 교환 **ComPtr** 지정 된 관리 인터페이스를 사용 하 여 **ComPtr**합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void Swap(  
   _Inout_ ComPtr&& r  
);  
  
void Swap(  
   _Inout_ ComPtr& r  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *r*  
 A **ComPtr**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)