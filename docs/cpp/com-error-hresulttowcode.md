---
title: _com_error::HRESULTToWCode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::HRESULTToWCode
dev_langs: C++
helpviewer_keywords: HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14c4cdf85e67bdb0acd8dbadd178e3fbd2dbaf54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Microsoft 전용**  
  
 32 비트 매핑합니다 `HRESULT` 에 16 비트 `wCode`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hr`  
 32 비트 `HRESULT` 16 비트 매핑될 수 있도록 `wCode`합니다.  
  
## <a name="return-value"></a>반환 값  
 16 비트 `wCode` 32 비트에서 매핑된 `HRESULT`합니다.  
  
## <a name="remarks"></a>설명  
 참조 [_com_error:: wcode](../cpp/com-error-wcode.md) 자세한 정보에 대 한 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [_com_error:: wcode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error 클래스](../cpp/com-error-class.md)