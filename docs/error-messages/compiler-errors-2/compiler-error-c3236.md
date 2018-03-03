---
title: "컴파일러 오류 C3236 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3236
dev_langs:
- C++
helpviewer_keywords:
- C3236
ms.assetid: 4ef1871f-a348-44ae-922b-1e2081de20d0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5651732d7404180a36efa56a0686415f020193fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3236"></a>컴파일러 오류 C3236
제네릭을 명시적으로 인스턴스화할 수 없습니다.  
  
 컴파일러는 제네릭 클래스의 명시적 인스턴스화를 허용하지 않습니다.  
  
 다음 샘플에서는 C3236을 생성합니다.  
  
```  
// C3236.cpp  
// compile with: /clr  
generic<class T>  
public ref class X {};  
  
generic ref class X<int>;   // C3236  
```  
  
 다음 샘플에는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3236b.cpp  
// compile with: /clr /c  
generic<class T>  
public ref class X {};  
```