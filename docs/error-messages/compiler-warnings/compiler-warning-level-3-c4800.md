---
title: 컴파일러 경고 (수준 3) C4800 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4800
dev_langs:
- C++
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed4b14ae2f3af3218909d6cd4609f1f45d3d7cc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4800"></a>컴파일러 경고(수준 3) C4800  
  
> '*형식*': bool 'true' 또는 'false' (성능 경고)에 값을 강제 적용  
  
이 경고는이 아닌 한 값을 때 발생 `bool` 할당 또는 형식으로 강제 변환할 `bool`합니다. 할당 하 여이 메시지는 발생 하는 일반적으로 `int` 변수를 `bool` 변수 위치는 `int` 변수 값만 포함 **true** 및 **false**, 될 수 있습니다 형식으로 다시 선언할 `bool`합니다. 형식을 사용 하도록 식을 다시 작성할 수 없는 경우 `bool`, 추가 하 여 "`!=0`" 식 형식을 제공 하는 식과 `bool`합니다. 식 형식으로 캐스팅 `bool` 이 의도적인 경고를 비활성화 하지 않습니다.  
  
이 경고는 더 이상 Visual Studio 2017에 발생 합니다.  
  
## <a name="example"></a>예제
  
 다음 샘플에서는 C4800 경고가 발생 하 고를 해결 하는 방법을 보여 줍니다.  
  
```cpp  
// C4800.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
  
   // To fix, instead try:  
   // bool i = 0;  
  
   bool j = i;   // C4800  
   j++;  
}  
```