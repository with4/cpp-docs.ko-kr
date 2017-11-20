---
title: "컴파일러 경고 (수준 1) C4965 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4965
dev_langs: C++
helpviewer_keywords: C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cde1b35dc183065461d1a2e59c77089256774ab4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4965"></a>컴파일러 경고(수준 1) C4965
암시적 상자 정수 0; nullptr 또는 명시적 캐스트를 사용 하 여  
  
 Visual c + + 기능을 값 형식 명시적 boxing 합니다. C + + 표현 됩니다. boxed 없는 정수에 대 한 할당에 대 한 Managed Extensions를 사용 하 여 null 할당에 발생 하는 명령  
  
 자세한 내용은 참조 [Boxing](../../windows/boxing-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4965 경고가 발생 합니다.  
  
```  
// C4965.cpp  
// compile with: /clr /W1  
int main() {  
   System::Object ^o = 0;   // C4965  
  
   // the previous line is the same as the following line  
   // using Managed Extensions for C++  
   // System::Object *o = __box(0);  
  
   // OK  
   System::Object ^o2 = nullptr;  
   System::Object ^o3 = safe_cast<System::Object^>(0);  
}  
```