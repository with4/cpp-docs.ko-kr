---
title: _com_ptr_t::Release | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
dev_langs: C++
helpviewer_keywords: Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 207569a2ad719e907fc46ba2abdd80a0c2e6239e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release
**Microsoft 전용**  
  
 호출의 **릴리스** 의 멤버 함수 **IUnknown** 캡슐화 된 인터페이스 포인터입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
void Release( );  
  
```  
  
## <a name="remarks"></a>설명  
 호출 `IUnknown::Release` 캡슐화 된 인터페이스 포인터를 발생 시키는 `E_POINTER` 이 인터페이스 포인터가 있으면 오류 **NULL**합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)