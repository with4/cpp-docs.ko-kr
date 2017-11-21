---
title: "컴파일러 오류 C2645 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2645
dev_langs: C++
helpviewer_keywords: C2645
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aaccf62efbc5926f65ac2e59359e0c73e8d0e680
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2645"></a>컴파일러 오류 C2645
멤버의 포인터에 대 한 정규화 된 이름이 없습니다 (발견 ':: *')  
  
 멤버에 대 한 포인터의 선언에서 클래스를 지정 하지 않습니다.  
  
 다음 샘플에서는 C2645 오류가 생성 됩니다.  
  
```  
// C2645.cpp  
class A {};  
int main() {  
   int B::* bp;   // C2645 B not defined  
   int A::* ap;   // OK  
}  
```