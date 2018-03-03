---
title: "NMAKE 심각한 오류 U1070 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1070
dev_langs:
- C++
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5adf5321c96341cfce633a2329a52360be8a45da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE 심각한 오류 U1070
'매크로 이름' 매크로 정의에서 순환 됩니다.  
  
 지정한 매크로 정의는 정의 가진 지정한 매크로 포함 하는 매크로 포함 되어 있습니다. 순환 매크로 정의가 유효 하지 않습니다.  
  
## <a name="example"></a>예  
 다음 매크로 정의  
  
```  
ONE=$(TWO)  
TWO=$(ONE)  
```  
  
 다음과 같은 오류가 발생 합니다.  
  
```  
cycle in macro definition 'TWO'  
```