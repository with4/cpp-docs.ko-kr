---
title: _com_error::WCodeToHRESULT | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCodeToHRESULT
dev_langs:
- C++
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f777b1de83b19727bca5e1b498c5380604f6688
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404543"
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Microsoft 전용**  
  
 16 비트 매핑합니다 *wCode* 32 비트 hresult입니다.  
  
## <a name="syntax"></a>구문  
  
```    
static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 *WCode*  
 16 비트 *wCode* 32 비트 HRESULT에 매핑됩니다.  
  
## <a name="return-value"></a>반환 값  
 16 비트에서 매핑된 32 비트 HRESULT *wCode*합니다.  
  
## <a name="remarks"></a>설명  
 참조 된 [WCode](../cpp/com-error-wcode.md) 멤버 함수입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [_com_error:: wcode](../cpp/com-error-wcode.md)   
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error 클래스](../cpp/com-error-class.md)