---
title: _bstr_t::GetAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t::GetAddress
dev_langs: C++
helpviewer_keywords: GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c1b2b348277f7d33a32c8d0e6ad1fc80d51ec68d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress
**Microsoft 전용**  
  
 기존 문자열을 해제하고 새로 할당된 문자열의 주소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## <a name="return-value"></a>반환 값  
 `BSTR`로 래핑되는 `_bstr_t`에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `GetAddress`는 `_bstr_t`을 공유하는 모든 `BSTR` 개체에 영향을 줍니다. 두 개 이상의 `_bstr_t`는 복사 생성자와 `BSTR`를 사용하여 `operator=`을 공유할 수 있습니다.  
  
## <a name="example"></a>예  
 참조 [_bstr_t:: assign](../cpp/bstr-t-assign.md) 사용 하는 예제 `GetAddress`합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_bstr_t 클래스](../cpp/bstr-t-class.md)