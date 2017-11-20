---
title: "_abnormal_termination | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _abnormal_termination
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords: _abnormal_termination
dev_langs: C++
helpviewer_keywords: _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 17dbe8079972626439f2706061258265303f5226
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="abnormaltermination"></a>_abnormal_termination
시스템이 종료 처리기의 내부 목록을 실행하는 동안 [try-finally](../cpp/try-finally-statement.md) 문의 `__finally` 블록이 입력되었는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
int   _abnormal_termination(  
   );  
```  
  
## <a name="return-value"></a>반환 값  
 시스템이 스택을 *해제*하면 `true`이고 해제하지 않으면 `false`입니다.  
  
## <a name="remarks"></a>설명  
 해제 예외를 관리하기 위해 사용되는 내부 함수이며 사용자 코드에서 호출할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|_abnormal_termination|excpt.h|  
  
## <a name="see-also"></a>참고 항목  
 [try-finally 문](../cpp/try-finally-statement.md)