---
title: "컴파일러 오류 C3749 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3749
dev_langs:
- C++
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 49c231ed1337b683e501dd145055775867f6e2fc
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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

