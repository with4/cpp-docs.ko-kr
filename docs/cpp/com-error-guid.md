---
title: _com_error::GUID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::GUID
dev_langs:
- C++
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee1952e50251cfac7563357c7626ab8603589e4d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409691"
---
# <a name="comerrorguid"></a>_com_error::GUID
**Microsoft 전용**  
  
 호출 **ierrorinfo:: Getguid** 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## <a name="return-value"></a>반환 값  
 결과 반환 **ierrorinfo:: Getguid** 에 대 한는 **IErrorInfo** 내에 기록 된 개체는 `_com_error` 개체입니다. 없는 경우 **IErrorInfo** 반환 개체, 기록 `GUID_NULL`합니다.  
  
## <a name="remarks"></a>설명  
 호출 하는 동안 모든 오류는 **ierrorinfo:: Getguid** 메서드는 무시 됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)