---
title: 'Comptr:: booltype 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a4ec737c3f24899e50220c3e862283b88a826b9
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461166"
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>ComPtr::operator Microsoft::WRL::Details::BoolType 연산자
나타냅니다 여부는 **ComPtr** 인터페이스의 개체 수명을 관리 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## <a name="return-value"></a>반환 값  
 인터페이스와 연결 된 경우 **ComPtr**의 주소를 [boolstruct:: Member](../windows/boolstruct-member-data-member.md) 데이터 멤버가 고, 그렇지 않으면 **nullptr**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)   
 [ComPtr::Get 메서드](../windows/comptr-get-method.md)