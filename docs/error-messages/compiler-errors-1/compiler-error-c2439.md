---
title: "컴파일러 오류 C2439 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2439
dev_langs:
- C++
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6aa5c0dcfd12be6979b0872f001bf0bf26a6e6e7
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2439"></a>컴파일러 오류 C2439
'identifier': 멤버를 초기화할 수 없습니다  
  
 클래스, 구조체 또는 공용 구조체 멤버를 초기화할 수 없습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  간접 기본 클래스 또는 구조체를 초기화 하려고 합니다.  
  
2.  클래스 또는 구조체의 상속된 된 멤버를 초기화 하려고 합니다. 상속된 된 멤버 클래스 또는 구조체의 생성자에서 초기화 되어야 합니다.
