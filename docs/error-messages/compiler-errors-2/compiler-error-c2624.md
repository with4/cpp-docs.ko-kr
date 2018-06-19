---
title: 컴파일러 오류 C2624 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2624
dev_langs:
- C++
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9edeb5bdef57663d29bb4cfe5427e5bc3f43b7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230666"
---
# <a name="compiler-error-c2624"></a>컴파일러 오류 C2624
'extern' 변수를 선언 하는 로컬 클래스를 사용할 수 없습니다.  
  
 지역 클래스 또는 구조체 선언에 사용할 수 없습니다 `extern` 변수입니다.  
  
 다음 샘플에서는 C2624 오류가 생성 됩니다.  
  
```  
// C2624.cpp  
int main() {  
   struct C {};  
   extern C ac;   // C2624  
}  
```