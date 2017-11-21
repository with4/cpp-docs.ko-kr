---
title: "컴파일러 오류 C2469 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2469
dev_langs: C++
helpviewer_keywords: C2469
ms.assetid: 3814bdff-581a-4d3e-8b47-8de6887cea69
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0b92a60a8e43c876466e21313a41eba1481a33ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2469"></a>컴파일러 오류 C2469
'operator': 'type' 개체를 할당할 수 없습니다.  
  
 연산자에 잘못된 형식이 전달되었습니다.  
  
 다음 샘플에서는 C2469를 생성합니다.  
  
```  
// C2469.cpp  
int main() {  
   int *i = new void;   // C2469  
   int *i = new int;   // OK  
}  
```