---
title: "컴파일러 경고 (수준 1) C4540 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4540
dev_langs:
- C++
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aaaef1edaa6af093ae03fe69231a9686e3d087a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4540"></a>컴파일러 경고(수준 1) C4540
dynamic_cast 액세스할 수 없거나 모호한 기본을 변환 하는 데 사용 테스트 실행 시간 ('type2'에 ' type1')이 실패 합니다.  
  
 사용한 `dynamic_cast` 다른 한 형식에서 변환할 수 있습니다. 컴파일러에서 확인는 캐스트는 항상 실패 (반환 **NULL**) 기본 클래스에 액세스할 수 없기 때문에 (`private`예를 들어) 모호 합니다 (두 번 이상 클래스 계층 구조의 예 표시).  
  
 다음에서는이 경고의 예를 보여 줍니다. 클래스 **B** 클래스에서 파생 된 **A**합니다. 프로그램은 사용 `dynamic_cast` 클래스 캐스팅 **B** (파생된 클래스) 클래스에 **A**는 항상 실패 클래스 **B** 은 `private` 이므로 액세스할 수 없습니다. 액세스를 변경 **A** 를 **공용** 하면 경고가 해결 됩니다.  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```