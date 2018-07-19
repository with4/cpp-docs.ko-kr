---
title: 컴파일러 오류 C2870 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2870
dev_langs:
- C++
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5fe9f47a96422493d6d731a18add8c23ff683f14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243491"
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