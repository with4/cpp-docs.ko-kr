---
title: "컴파일러 오류 C2827 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2827
dev_langs:
- C++
helpviewer_keywords:
- C2827
ms.assetid: cb3e5814-0c92-40e4-b620-98578ae3003a
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e061c619ca936afaefe392fb808a22c1a19a27ba
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2827"></a>컴파일러 오류 C2827
'operator 연산자' 단항 폼을 전역으로 재정의할 수 없습니다.  
  
 연산자는 개체의 외부에서 단항 형식을 사용할 수 없습니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  개체에 로컬 오버 로드 된 연산자를 확인 합니다.  
  
2.  적절 한 단항 연산자를 오버 로드를 선택 합니다.
