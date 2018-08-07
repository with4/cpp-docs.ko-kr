---
title: 컴파일러 경고 (수준 4) C4702 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4702
dev_langs:
- C++
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29c2d6b0328fd8dd4cd6f9a226253036b62d03ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295758"
---
# <a name="compiler-warning-level-4-c4702"></a>컴파일러 경고(수준 4) C4702
코드에 접근할 수  
  
 이 경고는 Visual Studio.NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과: 코드에 접근할 수 있습니다. C4702를 생성 합니다 (백 엔드) 컴파일러에서 접근할 수 없는 코드를 감지한 경우 수준 4 경고입니다.  
  
 Visual c + +의 Visual Studio.NET 2003와 Visual Studio.NET 버전에 적용 되는 코드에 대 한 접근할 수 없는 코드를 제거 하거나 모든 소스 코드를 일부 실행 흐름을에 연결할 수 있는지 확인 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4702 합니다.  
  
```  
// C4702.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main() {  
   return 1;  
   printf_s("I won't print.\n");   // C4702 unreachable  
}  
```  
  
## <a name="example"></a>예제  
 로 컴파일할 때 **/GX**, **/EHc**, **/EHsc**, 또는 **/EHac** extern C 함수를 사용 하 여 코드 수 있으며 연결할 수 없습니다. 때문에 extern C catch 블록 연결할 수 없어서, 함수는 throw 하지으로 가정 됩니다.  함수에서 throw 할 수 때문에이 경고가 잘못 되었다고 생각 되 면 사용 하 여 컴파일하고 **/EHa** 또는 **/EHs**throw 된 예외에 따라 합니다.  
  
 자세한 내용은 참조 [/EH (예외 처리 모델)](../../build/reference/eh-exception-handling-model.md) 자세한 정보에 대 한 합니다.  
  
 다음 샘플에서는 C4702 합니다.  
  
```  
// C4702b.cpp  
// compile with: /W4 /EHsc  
#include <iostream>  
  
using namespace std;  
extern "C" __declspec(dllexport) void Function2(){}  
  
int main() {  
   try {  
      Function2();  
   }  
   catch (...) {  
      cout << "Exp: Function2!" << endl;   // C4702  
   }  
}  
```