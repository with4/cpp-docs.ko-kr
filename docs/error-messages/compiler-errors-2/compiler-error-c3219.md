---
title: "컴파일러 오류 C3219 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3219
dev_langs:
- C++
helpviewer_keywords:
- C3219
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33816ce0cdc079d3531e72d777a4ac7c082025ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3219"></a>컴파일러 오류 C3219
'param': 제네릭 매개 변수는 여러 개의 비인터페이스('class')에 의해 제약을 받을 수 없습니다.  
  
 제네릭 매개 변수를 둘 이상의 관리되는 클래스로 제한할 수 없습니다.  
  
 다음 샘플에서는 C3219를 생성합니다.  
  
```  
// C3219.cpp  
// compile with: /clr  
ref class A {};  
ref class B {};  
  
generic <class T>  
where T : A, B  
ref class E {};   // C3219  
```  
  
 다음 샘플에는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3219b.cpp  
// compile with: /clr /c  
ref class A {};  
  
interface struct C {};  
  
generic <class T>  
where T : A  
ref class E {};  
```