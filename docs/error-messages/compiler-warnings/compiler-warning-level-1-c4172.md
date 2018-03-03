---
title: "컴파일러 경고 (수준 1) C4172 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4172
dev_langs:
- C++
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3cda1f5c578be76bbe98b60d014a70e970fcc2d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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