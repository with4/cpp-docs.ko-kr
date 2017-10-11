---
title: "컴파일러 오류 C3453 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3453
dev_langs:
- C++
helpviewer_keywords:
- C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a9dfd380a55d9233d0b421372e65fc3331c49cc9
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
