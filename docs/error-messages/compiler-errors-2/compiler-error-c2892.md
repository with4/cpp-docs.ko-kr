---
title: 컴파일러 오류 C2892 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2892
dev_langs:
- C++
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f348c56c4ae243738307f12fab568821840e7fe4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33241999"
---
# <a name="compiler-error-c2892"></a>컴파일러 오류 C2892
지역 클래스 멤버 템플릿을 가질 수 없습니다.  
  
 템플릿 멤버 함수는 함수에 정의 된 클래스에서 유효 하지 않습니다.  
  
 다음 샘플에서는 C2892 오류가 생성 됩니다.  
  
```  
// C2892.cpp  
int main() {  
   struct local {  
      template<class T>   // C2892  
      void f() {}  
   };  
}  
```