---
title: "컴파일러 오류 C2870 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2870
dev_langs:
- C++
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 75b9189795c7351745e9624cfb9cc11259834b76
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2870"></a>컴파일러 오류 C2870
'name': 네임 스페이스 정의 다른 네임 스페이스 정의 내에서 파일 범위에 있으며 즉시 나타나야 합니다.  
  
 네임 스페이스를 정의한 `name` 잘못 합니다. 네임 스페이스는 파일 범위 (블록 및 클래스 모든) 외부에서 정의 되어야 합니다 또는 다른 네임 스페이스 내에서 즉시 합니다.  
  
 다음 샘플에서는 C2870 오류가 생성 됩니다.  
  
```  
// C2870.cpp  
// compile with: /c  
int main() {  
   namespace A { int i; };   // C2870  
}  
```
