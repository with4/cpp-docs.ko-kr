---
title: _com_error::WCodeToHRESULT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::WCodeToHRESULT
dev_langs: C++
helpviewer_keywords: WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ca20bfa7574f604187734040b3ccc001d6aaf68d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Microsoft 전용**  
  
 16비트 `wCode`를 32비트 `HRESULT`로 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `wCode`  
 32비트 `wCode`로 매핑될 `HRESULT` 16비트입니다.  
  
## <a name="return-value"></a>반환 값  
 16비트 `HRESULT`에서 매핑된 32비트 `wCode`입니다.  
  
## <a name="remarks"></a>설명  
 참조는 [WCode](../cpp/com-error-wcode.md) 멤버 함수입니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error:: wcode](../cpp/com-error-wcode.md)   
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error 클래스](../cpp/com-error-class.md)