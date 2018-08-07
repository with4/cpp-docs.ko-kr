---
title: _com_error::HelpFile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpFile
dev_langs:
- C++
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3afcda41d5dc4ad3cc1fd74ed5449d574946f1e5
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402044"
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile
**Microsoft 전용**  
  
 호출 `IErrorInfo::GetHelpFile` 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
_bstr_t HelpFile() const;  
```  
  
## <a name="return-value"></a>반환 값  
 결과 반환 합니다 `IErrorInfo::GetHelpFile` 에 대 한는 `IErrorInfo` 내에 기록 된 개체는 `_com_error` 개체입니다. 결과 BSTR은 `_bstr_t` 개체에 캡슐화됩니다. 없으면 `IErrorInfo` 는 빈 반환 기록 `_bstr_t`합니다.  
  
## <a name="remarks"></a>설명  
 호출 하는 동안 모든 오류를 `IErrorInfo::GetHelpFile` 메서드는 무시 됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [_com_error 클래스](../cpp/com-error-class.md)