---
title: 컴파일러 오류 C3142 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3142
dev_langs:
- C++
helpviewer_keywords:
- C3142
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86ba6b66e49cb08dff1c3581eb06145148601b88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3142"></a>컴파일러 오류 C3142
'property_name': 속성의 주소를 가져올 수 없습니다  
  
 속성의 주소를 개발자에 게 사용할 수 없는 경우  
  
 다음 샘플에서는 C3142 오류가 생성 됩니다.  
  
```  
// C3142_2.cpp  
// compile with: /clr  
using namespace System;  
ref class CSize {  
private:  
   property int Size {  
      int get();  
   }  
};  
  
int main() {  
    &CSize::Size; // C3142  
}  
```  
