---
title: 컴파일러 오류 C3453 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3453
dev_langs:
- C++
helpviewer_keywords:
- C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f21a5833c618c5a5dfcc9ff2b608c5ec15bd1aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257037"
---
# <a name="compiler-error-c3453"></a>컴파일러 오류 C3453
'attribute': 'assembly' 한정자가 일치하지 않아 특성이 적용되지 않았습니다.  
  
 어셈블리 또는 모듈 수준 특성만 독립 실행형 명령으로 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3453을 생성합니다.  
  
```  
// C3453.cpp  
// compile with: /clr /c  
[assembly:System::CLSCompliant(true)]   // C3453  
// try the following line instead  
// [assembly:System::CLSCompliant(true)];  
ref class X {};  
```