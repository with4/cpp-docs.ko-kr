---
title: "컴파일러 오류 c 2057 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2057
dev_langs: C++
helpviewer_keywords: C2057
ms.assetid: 038a99d6-1f5a-42fa-8449-03b4ff11ee0b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12cf150a5c9ea866c195f3b7366a9ff9608bc10f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2057"></a>컴파일러 오류 c 2057
상수 식이 필요합니다.  
  
 컨텍스트에는 컴파일 시간에 값이 인식되는 상수 식이 필요합니다.  
  
 컴파일러는 해당 형식의 인스턴스에 대한 공간을 할당하기 위해 컴파일 시간에 형식의 크기를 알고 있어야 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2057을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2057.cpp  
int i;  
int b[i];   // C2057 - value of i is unknown at compile time  
int main() {  
   const int i = 8;  
   int b[i]; // OK - value of i is fixed and known to compiler  
}  
```  
  
## <a name="example"></a>예  
 C에서는 상수 식에 대해 보다 제한적인 규칙을 제공합니다.  다음 샘플에서는 C2057을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2057b.c  
#define ArraySize1 10  
int main() {   
   const int ArraySize2 = 10;   
   int h[ArraySize2];   // C2057 - C does not allow variables here  
   int h[ArraySize1];   // OK - uses preprocessor constant  
}  
```