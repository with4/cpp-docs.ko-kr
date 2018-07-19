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
ms.openlocfilehash: e324a84a16874a7e33f8687943b1302fbdd73a7a
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939028"
---
# <a name="comerrorguid"></a>_com_error::GUID
**Microsoft 전용**  
  
 호출 `IErrorInfo::GetGUID` 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## <a name="return-value"></a>반환 값  
 결과 반환 합니다 `IErrorInfo::GetGUID` 에 대 한는 `IErrorInfo` 내에 기록 된 개체는 `_com_error` 개체입니다. 없으면 `IErrorInfo` 개체는 기록 GUID_NULL를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 호출 하는 동안 모든 오류를 `IErrorInfo::GetGUID` 메서드는 무시 됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)