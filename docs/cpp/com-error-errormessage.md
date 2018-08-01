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
ms.openlocfilehash: 9367e92110ba7fb232e89b9d950e491e5e8da5c7
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407171"
---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage
**Microsoft 전용**  
  
 에 저장 된 HRESULT에 대 한 문자열 메시지를 검색 합니다 `_com_error` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
const TCHAR * ErrorMessage( ) const throw( );  
```  
  
## <a name="return-value"></a>반환 값  
 내에 기록 된 HRESULT에 대 한 문자열 메시지를 반환 합니다 `_com_error` 개체입니다. HRESULT가 매핑된 16 비트 [wCode](../cpp/com-error-wcode.md), 일반 메시지 "`IDispatch error #<wCode>`"이 반환 됩니다. 메시지가 발견되지 않으면 일반 메시지 "`Unknown error #<hresult>`"가 반환됩니다. 반환 된 문자열은 유니코드 또는 _UNICODE 매크로의 상태에 따라 멀티 바이트 문자열  
  
## <a name="remarks"></a>설명  
 내에 기록 된 HRESULT에 대 한 적절 한 시스템 메시지 텍스트를 검색 합니다 `_com_error` 개체입니다. Win32를 호출 하 여 시스템 메시지 텍스트를 가져옵니다 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) 함수입니다. 반환된 문자열은 `FormatMessage` API에 의해 할당되고, `_com_error` 개체가 소멸될 때 해제됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [_com_error 클래스](../cpp/com-error-class.md)