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
ms.openlocfilehash: c9ad0cbfa614c132a75e25f46b34e37ec3a5fc64
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407006"
---
# <a name="comerrorwcode"></a>_com_error::WCode
**Microsoft 전용**  
  
 캡슐화 된 HRESULT에 매핑된 16 비트 오류 코드를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
WORD WCode ( ) const throw( );  
```  
  
## <a name="return-value"></a>반환 값  
 HRESULT 0x80040200 ~ 0x8004FFFF 이면 범위 안에 있는 경우는 `WCode` 에서 0x80040200 뺀 값에 HRESULT를 반환 하는 메서드, 그렇지 않으면 0을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 `WCode` 메서드 COM 지원 코드에서 발생 하는 매핑을 실행 취소를 사용 합니다. 에 대 한 래퍼를 `dispinterface` 속성 또는 메서드 호출 인수 및 호출을 패키지 하는 지원 루틴 `IDispatch::Invoke`합니다. 경우 오류 HRESULT가 반환 될 때의 `DISP_E_EXCEPTION` 반환 되 면 오류 정보에서 검색 되는 `EXCEPINFO` 구조에 전달 `IDispatch::Invoke`합니다. 오류 코드 수에 저장 하는 16 비트 값을 `wCode` 의 멤버는 `EXCEPINFO` 구조 또는 전체 32 비트 값을 `scode` 소속을 `EXCEPINFO` 구조. 경우는 16 비트 `wCode` 반환 되 면 먼저 32 비트 오류 HRESULT에 매핑할 수 해야 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error 클래스](../cpp/com-error-class.md)