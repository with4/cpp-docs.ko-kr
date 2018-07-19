---
title: _com_ptr_t::Release | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a8a734eae486ca5e88009301b13d71b21473d9f
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939258"
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release
**Microsoft 전용**  
  
 호출 된 `Release` 멤버 함수 `IUnknown` 캡슐화 된 인터페이스 포인터에 대 한 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
void Release( );  
  
```  
  
## <a name="remarks"></a>설명  
 호출 `IUnknown::Release` 이 인터페이스 포인터가 null 인 경우 캡슐화 된 인터페이스 포인터에 대 한 E_POINTER 오류를 발생 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)