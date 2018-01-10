---
title: "컴파일러 경고 (수준 4) C4510 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4510
dev_langs: C++
helpviewer_keywords: C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4bfef2780f338357b600f8fae28559d4c7c00e49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4510"></a>컴파일러 경고(수준 4) C4510
'class': 기본 생성자를 생성할 수 없습니다  
  
 사용자 정의 생성자가 없습니다 만든와 컴파일러에서 지정된 된 클래스에 대 한 기본 생성자를 생성할 수 없습니다. 이 형식의 개체를 만들 수 없습니다.  
  
 와 같은 경우 컴파일러는 기본 생성자를 생성 하지 못하게 하는 포함 하 여:  
  
-   Const 데이터 멤버입니다.  
  
-   참조 데이터 멤버입니다.  
  
 이러한 멤버를 초기화 하는 클래스에 대 한 사용자 정의 기본 생성자를 만들 필요가 있습니다.  
  
 다음 샘플에서는 C4510 오류가 생성 됩니다.  
  
```  
// C4510.cpp  
// compile with: /W4  
struct A {  
   const int i;  
   int &j;  
   A& operator=( const A& ); // C4510 expected  
   // uncomment the following line to resolve this C4510  
   // A(int ii, int &jj) : i(ii), j(jj) {}  
};   // C4510  
  
int main() {  
}  
```