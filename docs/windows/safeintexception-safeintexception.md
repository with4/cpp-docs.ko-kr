---
title: 'Safeintexception:: Safeintexception | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs: C++
helpviewer_keywords: SafeIntException, constructor
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: d9a1e2666aef593cde385f121065397226bad9d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="safeintexceptionsafeintexception"></a>SafeIntException::SafeIntException

          `SafeIntException` 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
SafeIntException();  
  
SafeIntException(  
   SafeIntError code  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `code`  
 발생 한 오류를 설명 하는 열거형된 데이터 값입니다.  
  
## <a name="remarks"></a>설명  
 에 가능한 값은 `code` Safeint.h 파일에 정의 됩니다. 편의 위해 사용할 수 있는 값은 아래에 나열 되어 있습니다.  
  
-   `SafeIntNoError`  
  
-   `SafeIntArithmeticOverflow`  
  
-   `SafeIntDivideByZero`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>참고 항목  
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeIntException 클래스](../windows/safeintexception-class.md)   
 [SafeInt 클래스](../windows/safeint-class.md)