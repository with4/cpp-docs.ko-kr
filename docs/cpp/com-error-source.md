---
title: _com_error::Source | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Source
dev_langs:
- C++
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f904fa11195c27f8e08856ef391d0ba8adbedece
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939679"
---
# <a name="comerrorsource"></a>_com_error::Source
**Microsoft 전용**  
  
 호출 `IErrorInfo::GetSource` 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## <a name="return-value"></a>반환 값  
 결과 반환 합니다 `IErrorInfo::GetSource` 에 대 한는 `IErrorInfo` 내에 기록 된 개체는 `_com_error` 개체입니다. 결과 BSTR은 `_bstr_t` 개체에 캡슐화됩니다. 없으면 `IErrorInfo` 는 빈 반환 기록 `_bstr_t`합니다.  
  
## <a name="remarks"></a>설명  
 호출 하는 동안 모든 오류를 `IErrorInfo::GetSource` 메서드는 무시 됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)