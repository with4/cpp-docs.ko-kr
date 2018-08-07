---
title: 컴파일러 경고 (수준 3) C4534 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4534
dev_langs:
- C++
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b765f5f654c8d533b0ae22d874e7657cd10d667
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293035"
---
# <a name="compiler-warning-level-3-c4534"></a>컴파일러 경고(수준 3) C4534
'constructor'를 기본 인수 때문에 ' class' 클래스에 대 한 기본 생성자가 됩니다.  
  
 관리 되지 않는 클래스 기본값이 있는 매개 변수와 함께 생성자를 보유할 수 있으며 컴파일러가 생성자는 기본 생성자로 사용 합니다. 클래스에 표시 된 `value` 키워드로 사용 하지 것입니다 생성자는 기본 값으로 해당 매개 변수에 대 한 기본 생성자입니다.  
  
 자세한 내용은 참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C4534 오류가 생성 됩니다.  
  
```  
// C4534.cpp  
// compile with: /W3 /clr /WX  
value class MyClass {  
public:  
   int ii;  
   MyClass(int i = 9) {   // C4534, will not be the default constructor  
      i++;  
   }  
};  
  
int main() {  
   MyClass ^ xx = gcnew MyClass;  
   xx->ii = 0;  
}  
```