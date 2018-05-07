---
title: 컴파일러 오류 C3749 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3749
dev_langs:
- C++
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78de0c696123375c11e5c11e64223858b57451ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3749"></a>컴파일러 오류 C3749
'attribute': 사용자 지정 특성은 함수 안에서 사용할 수 없습니다  
  
 사용자 지정 특성은 함수 안에서 사용할 수 없습니다. 사용자 지정 특성에 대 한 자세한 내용은 항목을 참조 하십시오. [특성](../../windows/attribute.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3749 오류가 생성 됩니다.  
  
```  
// C3749a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
public ref struct ABC : public Attribute {  
   ABC() {}  
};  
  
void f1() { [ABC]; };  // C3749  
```  
