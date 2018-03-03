---
title: "컴파일러 오류 C3234 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3234
dev_langs:
- C++
helpviewer_keywords:
- C3234
ms.assetid: ebefc15a-e40d-424b-a3dd-d7e185d0ed7b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c9f1002b727053d4477095f546b36b159ee05fca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3234"></a>컴파일러 오류 C3234
제네릭 클래스는 제네릭 형식 매개 변수에서 상속할 수 없습니다.  
  
 제네릭 클래스는 제네릭 형식 매개 변수에서 상속할 수 없습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3234를 생성합니다.  
  
```  
// C3234.cpp  
// compile with: /clr /c  
generic <class T>  
public ref class C : T {};   // C3234  
// try the following line instead  
// public ref class C {};  
```