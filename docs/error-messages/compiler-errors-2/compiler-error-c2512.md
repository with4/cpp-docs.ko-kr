---
title: "컴파일러 오류 C2512 | Microsoft Docs"
ms.custom: 
ms.date: 02/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2512
dev_langs:
- C++
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57dbb542eee7e893253e6c3bdd3410c605a8d2db
ms.sourcegitcommit: 8ae12a602244a5853e941e5e8806e3545d876844
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2018
---
# <a name="compiler-error-c2512"></a>컴파일러 오류 C2512

> '*식별자*': 사용할 수 있는 적절 한 기본 생성자 없음  

A *기본 생성자*를 인수 없이, 필요한 생성자는 지정 된 클래스, 구조체 또는 공용 구조체에 사용할 수 없습니다. 컴파일러는 없는 사용자 정의 생성자가 제공 하는 경우에 기본 생성자를 제공 합니다.

Void가 아닌 매개 변수를 사용 하는 생성자를 제공 하는 경우 (예: 배열 요소)로 매개 변수 없이 만들 클래스를 허용 하려면 기본 생성자도 제공 해야 합니다. 기본 생성자는 모든 매개 변수에 기본값을 사용하는 생성자일 수 있습니다.

## <a name="example"></a>예

C 2512 오류의 일반적인 원인은 인수를 사용 하는 클래스 또는 구조체 생성자를 정의 하는 경우 이며 다음 클래스나 인수 없이 구조체의 인스턴스를 선언 하려고 합니다. 예를 들어 `struct B` 아래 필요로 하는 생성자를 선언는 `char *` 인수를 제외 하 고 인수를 받지 않는 합니다. `main`, B의 인스턴스가 선언 되지만 없습니다 인수를 제공 합니다. 2.에 대 한 기본 생성자를 찾을 수 없는 때문에 컴파일러가 c 2512를 생성

```cpp
// C2512.cpp
// Compile with: cl /W4 c2512.cpp
// C2512 expected
struct B {
   B (char *) {}
   // Uncomment the following line to fix.
   // B() {}
};

int main() {
   B b;   // C2512 - This requires a default constructor
}
```

와 같은 구조체 또는 클래스에 대 한 기본 생성자를 정의 하 여이 문제를 해결할 수 `B() {}`, 또는 모든 인수가 기본값을 갖는 같은 생성자 `B (char * = nullptr) {}`합니다.
