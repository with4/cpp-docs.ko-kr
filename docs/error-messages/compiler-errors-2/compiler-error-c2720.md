---
title: "컴파일러 오류 C2720 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2720
dev_langs: C++
helpviewer_keywords: C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 10c273d2c39d81397584ce674187057131542e89
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2720"></a>컴파일러 오류 C2720  
  
> '*식별자*': '*지정자*' 멤버에 대해 잘못 된 저장소 클래스 지정자  
  
선언 외부의 클래스 멤버에서 저장소 클래스를 사용할 수 없습니다. 이 오류를 해결 하려면 제거 불필요 한 [저장소 클래스](../../cpp/storage-classes-cpp.md) 클래스 선언 외부 멤버의 정의에서 지정자입니다.  
  
## <a name="example"></a>예제  
  
다음 샘플에서는 C2720 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```cpp  
// C2720.cpp  
struct S {  
   static int i;  
};  
static S::i;   // C2720 - remove the unneeded 'static' to fix it  
```