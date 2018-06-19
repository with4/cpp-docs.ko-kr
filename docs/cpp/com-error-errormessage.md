---
title: _com_error::ErrorMessage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c16b8bb6859cd65b534d804764257b901050995b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411239"
---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage
**Microsoft 전용**  
  
 `HRESULT` 개체에 저장된 `_com_error`에 대한 문자열 메시지를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
const TCHAR * ErrorMessage( ) const throw( );  
  
```  
  
## <a name="return-value"></a>반환 값  
 `HRESULT` 개체 내에 기록된 `_com_error`에 대한 문자열 메시지를 반환합니다. 경우는 `HRESULT` 매핑된 16 비트 [wCode](../cpp/com-error-wcode.md), 일반 메시지 "`IDispatch error #<wCode>`"이 반환 됩니다. 메시지가 발견되지 않으면 일반 메시지 "`Unknown error #<hresult>`"가 반환됩니다. 반환 된 문자열은 유니코드 또는 상태에 따라 멀티 바이트 문자열은 **_UNICODE** 매크로입니다.  
  
## <a name="remarks"></a>설명  
 `HRESULT` 개체 내에 기록된 `_com_error`에 대한 적절한 시스템 메시지 텍스트를 검색합니다. 시스템 메시지 텍스트는 Win32를 호출 하 여 가져온 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) 함수입니다. 반환된 문자열은 `FormatMessage` API에 의해 할당되고, `_com_error` 개체가 소멸될 때 해제됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error 클래스](../cpp/com-error-class.md)