---
title: _com_error::Description | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 848709fa6cbbbfb4166750f86540de2433a73023
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404030"
---
# <a name="comerrordescription"></a>_com_error::Description
**Microsoft 전용**  
  
 호출 `IErrorInfo::GetDescription` 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
_bstr_t Description( ) const;  
```  
  
## <a name="return-value"></a>반환 값  
 결과 반환 합니다 `IErrorInfo::GetDescription` 에 대 한는 `IErrorInfo` 내에 기록 된 개체는 `_com_error` 개체입니다. 결과 `BSTR`은 `_bstr_t` 개체에 캡슐화됩니다. 없으면 `IErrorInfo` 는 빈 반환 기록 `_bstr_t`합니다.  
  
## <a name="remarks"></a>설명  
 호출 된 `IErrorInfo::GetDescription` 함수와 검색 `IErrorInfo` 내에 기록 된는 `_com_error` 개체입니다. 호출 하는 동안 모든 오류를 `IErrorInfo::GetDescription` 메서드는 무시 됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [_com_error 클래스](../cpp/com-error-class.md)