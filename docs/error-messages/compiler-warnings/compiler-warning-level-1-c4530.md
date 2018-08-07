---
title: 컴파일러 경고 (수준 1) C4530 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4530
dev_langs:
- C++
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74804aa3ea0450c08710a5d0818eae67ce9b556e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283327"
---
# <a name="compiler-warning-level-1-c4530"></a>컴파일러 경고(수준 1) C4530
C + + 예외 처리기가 사용 되었지만 해제 의미 체계가 활성화 되지 않았습니다. /EHsc를 지정 합니다.  
  
 C + + 예외 처리를 사용 하지만 [/EHsc](../../build/reference/eh-exception-handling-model.md) 선택 하지 않았습니다.  
  
 /EHsc 옵션이 설정 되지 않은 경우에 throw 및 catch 함수 간의 프레임에 대 한 자동 저장 된 개체 소멸 되지 않습니다. 그러나 자동 저장 된 개체에서 만든는 **시도** 또는 **catch** 블록 소멸 됩니다.  
  
 다음 샘플에서는 C4530 오류가 생성 됩니다.  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 경고를 해결 하려면 /ehsc 예제를 컴파일하십시오.