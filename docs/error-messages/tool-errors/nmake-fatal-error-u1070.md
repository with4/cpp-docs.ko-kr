---
title: NMAKE 심각한 오류 U1070 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1070
dev_langs:
- C++
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fe39a5d6f6074596561cd8e32f7b9428bc60f6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE 심각한 오류 U1070
'매크로 이름' 매크로 정의에서 순환 됩니다.  
  
 지정한 매크로 정의는 정의 가진 지정한 매크로 포함 하는 매크로 포함 되어 있습니다. 순환 매크로 정의가 유효 하지 않습니다.  
  
## <a name="example"></a>예제  
 다음 매크로 정의  
  
```  
ONE=$(TWO)  
TWO=$(ONE)  
```  
  
 다음과 같은 오류가 발생 합니다.  
  
```  
cycle in macro definition 'TWO'  
```