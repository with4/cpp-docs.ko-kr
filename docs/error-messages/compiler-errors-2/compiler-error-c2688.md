---
title: "컴파일러 오류 C2688 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2688
dev_langs: C++
helpviewer_keywords: C2688
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b398ec1102ff5d5c795e6734e65564d11cd0ce3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2688"></a>컴파일러 오류 C2688
'C2:: fgrv': 공변 (covariant) 반환 여러 대 인 또는 가상 상속 varargs 함수에 대해 지원 되지 않습니다  
  
 공변 (covariant) 반환 형식은 함수에 변수 인수가 포함 된 경우 Visual c + +에서 지원 되지 않습니다.  
  
 이 오류를 해결 하려면 함수 정의 하거나 가변 인수를 사용 하거나 모든 가상 함수에 대해 동일 반환 값을 확인 하지 않습니다.  
  
 다음 샘플에서는 C2688 오류가 생성 됩니다.  
  
```  
// C2688.cpp  
struct G1 {};  
struct G2 {};  
struct G3 : G1, G2 {};  
struct G4 {};  
struct G5 {};  
struct G6 : G4, G5 {};  
struct G7 : G3, G6 {};  
  
struct C1 {  
   virtual G4& fgrv(int,...);  
};  
  
struct C2 : C1 {  
   virtual G7& fgrv(int,...);   // C2688, does not return G4&  
};  
```