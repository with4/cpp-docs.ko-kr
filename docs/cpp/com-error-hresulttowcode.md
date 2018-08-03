---
title: _com_error::HRESULTToWCode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HRESULTToWCode
dev_langs:
- C++
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0ddac28c4f39cdf11abbdf38c3af5d00c22413a
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401908"
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Microsoft 전용**  
  
 16 비트에서 32 비트 HRESULT 매핑됩니다 `wCode`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 *hr*  
 16 비트와 매핑되어야 32 비트 HRESULT `wCode`합니다.  
  
## <a name="return-value"></a>반환 값  
 16 비트 `wCode` 32 비트 HRESULT에서 매핑됩니다.  
  
## <a name="remarks"></a>설명  
 참조 [_com_error:: wcode](../cpp/com-error-wcode.md) 자세한 내용은 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [_com_error:: wcode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error 클래스](../cpp/com-error-class.md)