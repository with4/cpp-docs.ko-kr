---
title: _com_ptr_t::Detach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c04007df7d40e12f3f416b2f2cd437bdaf1314f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach
**Microsoft 전용**  
  
 캡슐화된 인터페이스 포인터를 추출하고 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## <a name="remarks"></a>설명  
 추출 및 캡슐화 된 인터페이스 포인터를 반환 하 고 다음 캡슐화 된 포인터 저장소를 지우는 **NULL**합니다. 이 작업을 통해 인터페이스 포인터의 캡슐화를 제거합니다. 호출 하 여은 **릴리스** 반환 된 인터페이스 포인터입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)