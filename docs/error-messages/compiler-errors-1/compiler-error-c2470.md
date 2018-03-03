---
title: "컴파일러 오류 C2470 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2470
dev_langs:
- C++
helpviewer_keywords:
- C2470
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 834ad581956c99e40e54a97f9d307691dce08600
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2470"></a>컴파일러 오류 C2470
'function': 함수 정의 보이지만 매개 변수 목록이 없습니다. 명백한 본문을 건너뜁니다.  
  
 함수 정의 인수 목록에 없습니다.  
  
 다음 샘플에서는 C2470 오류가 생성 됩니다.  
  
```  
// C2470.cpp  
int MyFunc {};  // C2470  
void MyFunc2() {};  //OK  
  
int main(){  
   MyFunc();  
   MyFunc2();  
}  
```