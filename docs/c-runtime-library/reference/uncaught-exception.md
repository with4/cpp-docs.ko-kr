---
title: __uncaught_exception | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __uncaught_exception
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords: __uncaught_exception
dev_langs: C++
helpviewer_keywords: __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2b43a6b08087dcaeeda7959eaadbee9c250f4de9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="uncaughtexception"></a>__uncaught_exception
예외가 하나 이상 throw되었지만 [try-catch](../../cpp/try-throw-and-catch-statements-cpp.md) 문의 해당 `catch` 블록에서 아직 처리되지 않았음을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
bool __uncaught_exception(  
   );  
```  
  
## <a name="return-value"></a>반환 값  
 `try` 블록에서 예외가 throw되는 시간부터 일치하는 `catch` 블록이 초기화될 때까지는 `true`이고 그 외의 경우에는 `false`입니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|__uncaught_exception|eh.h|  
  
## <a name="see-also"></a>참고 항목  
 [try, throw 및 catch 문(C++)](../../cpp/try-throw-and-catch-statements-cpp.md)