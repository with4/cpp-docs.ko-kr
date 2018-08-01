---
title: _com_ptr_t::AddRef | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::AddRef
dev_langs:
- C++
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4bf56e87b8b7949048b1e6006d3aa32f00af1462
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404261"
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef
**Microsoft 전용**  
  
 호출 된 `AddRef` 멤버 함수 `IUnknown` 캡슐화 된 인터페이스 포인터에 대 한 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void AddRef( );  
```  
  
## <a name="remarks"></a>설명  
 호출 `IUnknown::AddRef` 캡슐화 된 인터페이스 포인터에 대 한 발생을 `E_POINTER` 포인터가 null 인 경우 오류가 발생 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)