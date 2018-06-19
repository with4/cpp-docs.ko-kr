---
title: 컴파일러 오류 C3874 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3874
dev_langs:
- C++
helpviewer_keywords:
- C3874
ms.assetid: fd55fc05-69a7-4237-b3b7-dca1d5400b4f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb1224b1e5b14c0f34e10b7eff972d4014cccdff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268257"
---
# <a name="compiler-error-c3874"></a>컴파일러 오류 C3874
'function'의 반환 형식은 'int' 대신 'type' 해야 합니다.  
  
 함수에는 컴파일러에서 예상 된 반환 형식이 없습니다.  
  
 다음 샘플에서는 C3874 오류가 생성 됩니다.  
  
```  
// C3874b.cpp  
double main()  
{   // C3874  
}  
```