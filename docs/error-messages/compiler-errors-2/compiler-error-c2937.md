---
title: "컴파일러 오류 C2937 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2937
dev_langs: C++
helpviewer_keywords: C2937
ms.assetid: 95671ca3-79f7-4b56-a5f2-a92296da1629
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a82068c4994fa757a5345336b5132f4e64c76309
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2937"></a>컴파일러 오류 C2937
'class': type-class-id가 전역 typedef로 재정의되었습니다.  
  
 제네릭 또는 템플릿 클래스를 전역 `typedef`로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2937을 생성합니다.  
  
```  
// C2937.cpp  
// compile with: /c  
template<class T>   
struct TC { };  
typedef int TC<int>;   // C2937  
typedef TC<int> c;   // OK  
```  
  
 C2937은 제네릭을 사용하는 경우에도 발생할 수 있습니다.  
  
```  
// C2937b.cpp  
// compile with: /clr  
generic<class T>  
ref struct GC { };  
typedef int GC<int>;   // C2937  
typedef GC<int> xx;   // OK  
```