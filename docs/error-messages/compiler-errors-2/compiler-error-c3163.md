---
title: "컴파일러 오류 C3163 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3163
dev_langs:
- C++
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d3cbb5c5c3e8391b3a549fc0c34661dc86b492c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3163"></a>컴파일러 오류 C3163
'construct': 특성이 이전 선언과 일치 하지 않습니다.  
  
 정의에 적용 되는 특성 선언에 적용 되는 특성와 충돌 합니다.  
  
 C3163 해결 하는 한 가지 방법은 정방향 선언에서 특성을 제거 하는 합니다. 정방향 선언에 특성이 정의에 있는 특성 보다 작을 수 하거나 해야, 많아야 같아야 합니다.  
  
 C3163 오류의 가능한 원인은 Microsoft 소스 코드 주석 언어 (SAL) 작업이 포함 됩니다. 프로젝트를 사용 하 여 컴파일하지 않으면 SAL 매크로가 확장 하지 않고는 **/analyze** 플래그입니다. 사용 하 여 다시 시도 하지 않고 오류 없이 컴파일되지 / 분석 하는 프로그램 C3163를 throw 할 수 있습니다는 /analyze 옵션입니다. SAL에 대 한 자세한 내용은 참조 [SAL 주석을](../../c-runtime-library/sal-annotations.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 c3163 오류가 발생 합니다.  
  
```  
// C3163.cpp  
// compile with: /clr /c  
using namespace System;  
  
[CLSCompliant(true)] void f();  
[CLSCompliant(false)] void f() {}   // C3163  
// try the following line instead  
// [CLSCompliant(true)] void f() {}  
```  
  
## <a name="see-also"></a>참고 항목  
 [SAL 주석](../../c-runtime-library/sal-annotations.md)