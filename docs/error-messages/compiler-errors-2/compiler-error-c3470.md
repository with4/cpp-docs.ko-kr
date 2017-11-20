---
title: "컴파일러 오류 C3470 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3470
dev_langs: C++
helpviewer_keywords: C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7ae5a2d2d95c3ab6a521493874b416c87d4e5a9b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3470"></a>컴파일러 오류 C3470
'type': 클래스에 인덱서(인덱싱된 기본 속성)와 operator[]가 동시에 포함될 수 없습니다.  
  
 하나의 형식으로 기본 인덱서와 연산자[]를 모두 정의할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3470을 생성합니다.  
  
```  
// C3470.cpp  
// compile with: /clr  
using namespace System;  
  
ref class R {  
public:  
   property int default[int] {  
      int get(int i) {  
         return i+1;  
      }  
   }  
  
   int operator[](String^ s) { return Convert::ToInt32(s); }   // C3470  
};  
  
int main() {  
   R ^ r = gcnew R;  
   // return r[9] + r["32"] - 42;  
}  
```