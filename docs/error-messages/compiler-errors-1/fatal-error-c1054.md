---
title: 심각한 오류 C1054 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C1054
dev_langs:
- C++
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c39ba89a36791c56c0b71637cac388b28dc372f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1054"></a>심각한 오류 C1054
컴파일러 한계: 이니셜라이저가 너무 많이 중첩  
  
 코드는 중첩 제한에서 이니셜라이저의 (초기화 되는 형식의 조합에 따라 10-15 수준)를 초과 합니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  중첩을 줄이기 위해 초기화 중인 데이터 형식을 단순화 합니다.  
  
2.  선언 후 별도 문에 변수를 초기화 합니다.