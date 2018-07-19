---
title: 컴파일러 경고 (수준 1) C4172 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4172
dev_langs:
- C++
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 746442638820d0c81144611a678996dc4c8483b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276661"
---
# <a name="compiler-warning-level-1-c4172"></a>컴파일러 경고 (수준 1) C4172
지역 변수 또는 임시 주소를 반환합니다.  
  
 함수는 지역 변수 또는 임시 개체의 주소를 반환합니다. 지역 변수 및 임시 개체 삭제 됩니다는 함수가 반환 될 때 반환 되는 주소는 잘못 됩니다.  
  
 로컬 개체의 주소를 반환 하지 않는 되도록 함수를 다시 디자인 합니다.  
  
 다음 샘플에서는 C4172:  
  
```  
// C4172.cpp  
// compile with: /W1 /LD  
float f = 10;  
  
const double& bar() {  
// try the following line instead  
// const float& bar() {  
   return f;   // C4172  
}  
```