---
title: _com_ptr_t::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: aa14a5fb0e54971e19de1b46317d768e7fc06a2e
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtattach"></a>_com_ptr_t::Attach
**Microsoft 전용**  
  
 이 스마트 포인터 형식의 원시 인터페이스 포인터를 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      void Attach(  
   Interface* pInterface   
) throw( );  
void Attach(  
   Interface* pInterface,  
   bool fAddRef   
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pInterface`  
 원시 인터페이스 포인터입니다.  
  
 `fAddRef`  
 이 경우 **true**, 다음 `AddRef` 호출 됩니다. 이 경우 **false**, `_com_ptr_t` 개체 호출 하지 않고 원시 인터페이스 포인터의 소유권을 갖습니다 `AddRef`합니다.  
  
## <a name="remarks"></a>설명  
  
-   **연결 (**`pInterface`**)** `AddRef` 호출 되지 않습니다.     인터페이스 소유권이 이 `_com_ptr_t` 개체에 전달됩니다. **릴리스** 이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 시키기 위해 호출 됩니다.  
  
-   **연결 (** `pInterface` **,**`fAddRef`**)** 경우 `fAddRef` 은 **true**, `AddRef` 대 한 참조를 증가 하기 위해 호출 캡슐화 된 인터페이스 포인터에 대 한 수입니다.       경우 `fAddRef` 은 **false**,이 `_com_ptr_t` 개체 호출 하지 않고 원시 인터페이스 포인터의 소유권을 갖습니다 `AddRef`합니다. **릴리스** 이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 시키기 위해 호출 됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
