---
title: "ATL_URL_SCHEME 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs: C++
helpviewer_keywords: ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
caps.latest.revision: "7.2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cca9eaf9da116c241b4e137e8ca204b1a90b4595
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="atlurlscheme"></a>ATL_URL_SCHEME  

이 열거형의 멤버에서 인식 된 스키마에 대 한 상수를 제공 [CUrl](curl-class.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      enum ATL_URL_SCHEME{  
   ATL_URL_SCHEME_UNKNOWN = -1,  
   ATL_URL_SCHEME_FTP     = 0,  
   ATL_URL_SCHEME_GOPHER  = 1,  
   ATL_URL_SCHEME_HTTP    = 2,  
   ATL_URL_SCHEME_HTTPS   = 3,  
   ATL_URL_SCHEME_FILE    = 4,  
   ATL_URL_SCHEME_NEWS    = 5,  
   ATL_URL_SCHEME_MAILTO  = 6,  
   ATL_URL_SCHEME_SOCKS   = 7  
};  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
## <a name="see-also"></a>참고 항목  
 [개념](../active-template-library-atl-concepts.md)   
 [CUrl::SetScheme](curl-class.md#setscheme)   
 [CUrl::GetScheme](curl-class.md#getscheme)