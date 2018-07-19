---
title: 컴파일러 오류 C2505 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2505
dev_langs:
- C++
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fac405fc13b7696f752ea6455dcbf464318dca56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227663"
---
# <a name="compiler-error-c2505"></a>컴파일러 오류 C2505
'symbol': '__declspec(modifer)' 선언 또는 전역 개체 또는 정적 데이터 멤버의 정의에 적용 될 수 있습니다  
  
 A `__declspec` 전역 범위에서 사용 하도록 설계 된 한정자는 함수에 사용 했습니다.  
  
 자세한 내용은 [appdomain](../../cpp/appdomain.md) 및 [process](../../cpp/process.md)를 참조하세요.  
  
 다음 샘플에서는 C2505 오류가 생성 됩니다.  
  
```  
// C2505.cpp  
// compile with: /clr  
  
// OK  
__declspec(process) int ii;  
__declspec(appdomain) int jj;  
  
int main() {  
   __declspec(process) int i;   // C2505  
   __declspec(appdomain) int j;   // C2505  
}  
```