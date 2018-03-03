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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6efdea50fbc807175dbe67af27835dea9de7363e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3176"></a>컴파일러 오류 C3176
'type': 지역 값 형식을 선언할 수 없습니다.  
  
 클래스는 전역 범위에서 값 형식으로 선언할 수만 있습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3176 오류가 발생 합니다.  
  
```  
// C3176.cpp  
// compile with: /clr  
int main () {  
   enum class C {};   // C3176  
}  
```