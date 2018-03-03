---
title: "컴파일러 오류 C2206 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2206
dev_langs:
- C++
helpviewer_keywords:
- C2206
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 172a138f783ef829c1b8e691a1248a9feb2e77dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2206"></a>컴파일러 오류 C2206
'function': 형식 정의는 함수 정의에 사용할 수 없습니다.  
  
 `typedef` 가 함수 형식을 정의하는 데 사용됩니다.  
  
 다음 샘플에서는 C2206을 생성합니다.  
  
```  
// C2206.cpp  
typedef int functyp();  
typedef int MyInt;  
functyp func1 {};   // C2206  
int main() {  
   MyInt i = 0;   // OK  
}  
```