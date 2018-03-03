---
title: "Hstring:: Attach 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
dev_langs:
- C++
ms.assetid: 69451979-0014-4959-bc5c-1e4ab6fb28e4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 081b9ad1d3001c74f2b2c096f5f26fe96c413f68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hstringattach-method"></a>HString::Attach 메서드
현재 HString 개체가 지정 된 HString 개체를 연결합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
void Attach(  
       HSTRING hstr  
       ) throw()  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hstr`  
 기존 HString 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HString 클래스](../windows/hstring-class.md)