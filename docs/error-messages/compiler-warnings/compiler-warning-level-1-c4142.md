---
title: 컴파일러 경고 (수준 1) C4142 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4142
dev_langs:
- C++
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c87b7689cf11ab28c1a6377ff85e1594fd1b5fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284435"
---
# <a name="compiler-warning-level-1-c4142"></a>컴파일러 경고 (수준 1) C4142
형식 재정의가  
  
 형식이 생성된 된 코드에 영향을 주지 않는 방식으로 재정의 되었습니다.  
  
 다음과 같은 가능한 원인을 확인하여 수정하세요.  
  
-   파생된 클래스의 멤버 함수에 해당 멤버 함수에서 기본 클래스의 다른 반환 형식이 있습니다.  
  
-   으로 정의 된 형식에서 `typedef` 명령 서로 다른 구문을 사용 하 여 재정의 됩니다.  
  
 다음 샘플에서는 C4142 오류가 생성 됩니다.  
  
```  
// C4142.c  
// compile with: /W1  
float X2;  
X2 = 2.0 + 1.0;   // C4142  
  
int main() {  
   float X2;  
   X2 = 2.0 + 1.0;   // OK  
}  
```