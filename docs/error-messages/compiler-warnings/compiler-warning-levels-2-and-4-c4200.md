---
title: "컴파일러 경고 (수준 2 및 4) C4200 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4200
dev_langs: C++
helpviewer_keywords: C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f160476deb2ab3e4ad0ff00100305c934dfb14c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-2-and-4-c4200"></a>컴파일러 경고(수준 2 및 4) C4200
비표준 확장이 사용됨: 구조체/공용 구조체의 배열 크기가 0입니다.  
  
 구조체 또는 공용 구조체에 크기가 0인 배열이 포함되어 있음을 나타냅니다.  
  
 크기가 0인 배열의 선언은 Microsoft 확장입니다. 이로 인해 C++ 파일을 컴파일할 때는 수준 2 경고가, C 파일을 컴파일할 때는 수준 4 경고가 발생합니다. C++ 컴파일에서는 "UDT에 크기가 0인 배열이 있는 경우 복사 생성자 또는 복사 할당 연산자를 생성할 수 없습니다."라는 경고도 표시됩니다. 이 예제에서는 경고 C4200을 생성합니다.  
  
```cpp  
// C4200.cpp  
// compile by using: cl /W4 c4200.cpp  
struct A {  
    int a[0];  // C4200  
};  
int main() {  
}  
```  
  
 이 비표준 확장은 코드가 가변 길이의 외부 데이터 구조체와 상호 작용하도록 하는 데 사용되는 경우가 많습니다. 사용 중인 코드에 이러한 시나리오가 적용되는 경우에는 경고가 표시되지 않도록 설정할 수 있습니다.  
  
## <a name="example"></a>예  
  
```cpp  
// C4200b.cpp  
// compile by using: cl /W4 c4200a.cpp  
#pragma warning(disable : 4200)  
struct A {  
    int a[0];  
};  
int main() {  
}  
```