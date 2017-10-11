---
title: "컴파일러 오류 C3176 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3176
dev_langs:
- C++
helpviewer_keywords:
- C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ce046573ebeaf68f3b48d0e3d096b172bf26a66c
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3176"></a>컴파일러 오류 C3176
'type': 지역 값 형식을 선언할 수 없습니다.  
  
 클래스는 전역 범위에서 값 형식으로 선언할 수만 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3176 오류가 발생 합니다.  
  
```  
// C3176.cpp  
// compile with: /clr  
int main () {  
   enum class C {};   // C3176  
}  
```
