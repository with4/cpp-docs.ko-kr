---
title: _com_error::ErrorInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fbc735dfae1b30209eccfd14f1170826fb07680
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo
**Microsoft 전용**  
  
 검색 된 **IErrorInfo** 개체 생성자에 전달 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## <a name="return-value"></a>반환 값  
 원시 **IErrorInfo** 항목은 생성자에 전달 합니다.  
  
## <a name="remarks"></a>설명  
 캡슐화 된 검색 **IErrorInfo** 항목에 `_com_error` 개체 또는 **NULL** 없으면 **IErrorInfo** 항목이 기록 됩니다. 호출자에 게 호출 해야 **릴리스** 완료 되 면 반환된 된 개체에 사용 하 여 것입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)