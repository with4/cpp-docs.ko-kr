---
title: "Comptr:: booltype 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f98ca8068495be46b795d361c969c4feb2c24169
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>ComPtr::operator Microsoft::WRL::Details::BoolType 연산자
ComPtr이 인터페이스의 개체 수명을 관리하고 있는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## <a name="return-value"></a>반환 값  
 인터페이스는이 ComPtr의 주소와 연결 하는 경우는 [boolstruct:: Member](../windows/boolstruct-member-data-member.md) 데이터 멤버, 그렇지 않으면 `nullptr`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)   
 [ComPtr::Get 메서드](../windows/comptr-get-method.md)