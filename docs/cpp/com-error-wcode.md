---
title: '_com_error:: wcode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCode
dev_langs:
- C++
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1354d490446795e55b41fa0c548e8dd8aa38c71b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorwcode"></a>_com_error::WCode
**Microsoft 전용**  
  
 캡슐화된 `HRESULT`에 매핑되는 16비트 오류 코드를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## <a name="return-value"></a>반환 값  
 경우는 `HRESULT` 0x80040200 ~ 0x8004FFFF 이면 범위 내에서 **WCode** 메서드가 반환 되는 `HRESULT` 0x80040200; 뺀 그렇지 않으면 0을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 **WCode** 메서드는 COM 지원 코드에서 발생 하는 매핑을 실행 취소 하는 데 사용 됩니다. 에 대 한 래퍼는 **dispinterface** 속성 또는 메서드 호출의 인수 및 호출을 패키지 하는 지원 루틴 **idispatch:: Invoke**합니다. 반환 시 오류 `HRESULT` 의 `DISP_E_EXCEPTION` 반환 되 면 오류 정보에서 검색 됩니다는 **EXCEPINFO** 를 전달 하는 구조 **idispatch:: Invoke**합니다. 오류 코드 수에 저장 된 16 비트 값의 `wCode` 의 멤버는 **EXCEPINFO** 구조 또는에 완전 한 32 비트 값의 **scode** 의 멤버는 **EXCEPINFO**구조입니다. 16비트 `wCode`가 반환되면 먼저 32비트 오류 `HRESULT`에 매핑되어야 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error 클래스](../cpp/com-error-class.md)