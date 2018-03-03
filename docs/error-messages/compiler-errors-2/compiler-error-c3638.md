---
title: "컴파일러 오류 C3638 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3638
dev_langs:
- C++
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 879ccb667ce766a24cb9666ec74fb89728c9d8d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3638"></a>컴파일러 오류 C3638
'operator': 기본 boxing 및 unboxing 변환 연산자를 재정의할 수 없습니다  
  
 컴파일러는 암시적 boxing을 지원 하도록 각 관리 되는 클래스에 대 한 변환 연산자를 정의 합니다. 이 연산자를 재정의할 수 없습니다.  
  
 자세한 내용은 참조 [암시적 Boxing](../../windows/boxing-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C3638 오류가 생성 됩니다.  
  
```  
// C3638.cpp  
// compile with: /clr  
value struct V {  
   V(){}  
   static operator V^(V);   // C3638  
};  
  
int main() {  
   V myV;  
   V ^ pmyV = myV;   // operator supports implicit boxing  
}  
```