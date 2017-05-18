---
title: "컴파일러 오류 C3749 | Microsoft 문서"
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 20072ae0bdb55a6ee9cbac9d1ce0269991b839af
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3749"></a>컴파일러 오류 C3749
'attribute': 함수 내 사용자 지정 특성을 사용할 수 없습니다  
  
 함수 내 사용자 지정 특성을 사용할 수 없습니다. 사용자 지정 특성에 대 한 자세한 내용은 항목을 참조 하십시오. [특성](../../windows/attribute.md)합니다.  
  
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

