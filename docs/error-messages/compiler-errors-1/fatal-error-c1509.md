---
title: "심각한 오류 C1509 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1509
dev_langs: C++
helpviewer_keywords: C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22cb22ea2186b16fd98d2714779b2475c51d15bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1509"></a>심각한 오류 C1509
컴파일러 한계: ' function '함수에에서 예외 처리기 상태가 너무 많습니다. 함수를 단순화 합니다.  
  
 코드에서 예외 처리기 상태가 (32, 768 상태) 내부 한계를 초과 합니다.  
  
 가장 일반적인 원인은 함수에 사용자 지정 클래스 변수 및 산술 연산자는 복잡 한 식이 포함 되어 있습니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  공통 하위 식의 임시 변수를 지정 하 여 단순한 식을 사용 합니다.  
  
2.  함수를 좀 더 작은 함수로 분할 합니다.