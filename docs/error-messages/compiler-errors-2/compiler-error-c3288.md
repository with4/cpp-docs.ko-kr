---
title: "컴파일러 오류 C3288 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3288
dev_langs:
- C++
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9030ad9f46a36a1879d1c0f4f97b772e893b37ab
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3288"></a>컴파일러 오류 C3288
'type': 핸들 형식의 역참조가 잘못 되었습니다  
  
 컴파일러는 핸들 형식의 잘못 된 역참조를 발견 했습니다. 핸들 형식을 역 참조할 수 있으며 참조를 할당할 수 있습니다. 자세한 내용은 참조 [추적 참조 연산자](../../windows/tracking-reference-operator-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3288 오류가 발생 합니다.  
  
```  
// C3288.cpp  
// compile with: /clr  
ref class R {};  
int main() {  
   *(System::Object^) nullptr;   // C3288  
  
// OK  
   (System::Object^) nullptr;   // OK  
   R^ r;  
   R% pr = *r;  
}  
```
