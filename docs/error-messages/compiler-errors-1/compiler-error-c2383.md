---
title: "컴파일러 오류 C2383 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2383
dev_langs: C++
helpviewer_keywords: C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7f89545b9428bd5e901c72d895b5c23317646c26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2383"></a>컴파일러 오류 C2383
'*기호*':이 기호에 기본 인수를 사용할 수 없습니다  
  
 C + + 컴파일러는 함수에 대 한 포인터에 기본 인수를 허용 하지 않습니다.  
  
 이 코드의 Visual Studio 2005 이전 버전의 Visual c + + 컴파일러에서 수락한 하지만 이제 오류가 발생 합니다. 모든 버전의 Visual c + +에서 작동 하는 코드에 대 한 함수에 포인터 인수를 기본 값을 할당 하지 마십시오.  
  
## <a name="example"></a>예  
 다음 예제에서는 C2383, 오류가 발생 하는 경우 및 가능한 해결 방법을 보여 줍니다.  
  
```cpp  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```