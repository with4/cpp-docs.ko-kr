---
title: _com_error::operator = | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= _com_error objects
- = operator [C++], with specific Visual C++ objects
- operator = _com_error objects
ms.assetid: b9cc4094-d055-450c-b45a-0a95317488f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 744a4b344a336ec502e184e9be9ffb236c863708
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410634"
---
# <a name="comerroroperator-"></a>_com_error::operator =
**Microsoft 전용**  
  
 기존 `_com_error` 개체를 다른 개체에 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      _com_error& operator = (  
   const _com_error& that   
) throw ( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `that`  
 `_com_error` 개체입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)