---
title: "컴파일러 오류 C2081 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2081
dev_langs:
- C++
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 20f9f98ca03b9ed71d360b1b7c8bb64494a58416
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2081"></a>컴파일러 오류 C2081
'identifier': 정식 매개 변수 목록이 잘못 되었습니다 이름  
  
 식별자 구문 오류가 발생 했습니다.  
  
 이 오류는 형식 매개 변수 목록에 대 한 이전 스타일을 사용 하 여 발생할 수 있습니다. 형식 매개 변수 목록에 정식 매개 변수 형식을 지정 해야 합니다.  
  
 다음 샘플에서는 C2081 오류가 생성 됩니다.  
  
```  
// C2081.c  
void func( int i, j ) {}  // C2081, no type specified for j  
```  
  
 해결 방법:  
  
```  
// C2081b.c  
// compile with: /c  
void func( int i, int j ) {}  
```
