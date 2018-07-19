---
title: 컴파일러 오류 C3454 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3454
dev_langs:
- C++
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65e1aea19dbeab5c34a6b818afcb4cd4a7deda91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33263376"
---
# <a name="compiler-error-c3454"></a>컴파일러 오류 C3454
[attribute]는 클래스 선언에 사용할 수 없습니다.  
  
 클래스는 특성이 되도록 정의되어야 합니다.  
  
 자세한 내용은 [attribute](../../windows/attribute.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3454를 생성합니다.  
  
```  
// C3454.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute]   // C3454  
ref class Attr1;  
  
[attribute]   // OK  
ref class Attr2 {};  
```