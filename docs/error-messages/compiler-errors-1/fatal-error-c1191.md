---
title: 심각한 오류 C1191 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1191
dev_langs:
- C++
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf700db0e415fd7886cd8ba845f06a2d8f6c3249
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226345"
---
# <a name="fatal-error-c1191"></a>심각한 오류 C1191
'dll' 전역 범위 에서만 가져올 수 있습니다.  
  
 /Clr 프로그래밍을 사용 하는 프로그램에 mscorlib.dll을 가져오는 명령 없습니다 함수나 네임 스페이스에 나타나지만 전역 범위에 표시 되어야 합니다.  
  
 다음 샘플에서는 C1191 오류가 생성 됩니다.  
  
```  
// C1191.cpp  
// compile with: /clr  
namespace sample {  
   #using <mscorlib.dll>   // C1191 not at global scope  
}  
```  
  
 해결 방법:  
  
```  
// C1191b.cpp  
// compile with: /clr /c  
#using <mscorlib.dll>  
namespace sample {}  
```