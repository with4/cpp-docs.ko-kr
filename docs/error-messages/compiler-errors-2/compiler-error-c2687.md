---
title: 컴파일러 오류 C2687 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2687
dev_langs:
- C++
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b54c3be7a3706dd5471b21c2a1779e9990eae678
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233020"
---
# <a name="compiler-error-c2687"></a>컴파일러 오류 C2687
'type': 예외 선언은 'void' 수 없고는 불완전 한 형식 또는 포인터 또는 불완전 한 형식에 대 한 참조를 표시 합니다.  
  
 예외 선언의 일부로 형식에 대해 정의 되 고 void가 아니어야 이어야 합니다.  
  
 다음 샘플에서는 C2687 오류가 생성 됩니다.  
  
```  
// C2687.cpp  
class C;  
  
int main() {  
   try {}  
   catch (C) {}   // C2687 error  
}  
```  
  
 해결 방법:  
  
```  
// C2687b.cpp  
// compile with: /EHsc  
class C {};  
  
int main() {  
   try {}  
   catch (C) {}  
}  
```