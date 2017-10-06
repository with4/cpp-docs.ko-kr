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
- Detach method
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: f61b0fb05f182ef2723fdcc564fd697f490aed20
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

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
