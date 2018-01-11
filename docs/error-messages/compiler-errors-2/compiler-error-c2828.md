---
title: "컴파일러 오류 C2828 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2828
dev_langs: C++
helpviewer_keywords: C2828
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc78f876056c09a27de3766812dbc22eefe1848d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2828"></a>컴파일러 오류 C2828
'operator 연산자' 이진 양식으로 전역으로 재정의할 수 없습니다.  
  
 연산자는 개체의 외부에서 이진 형식을 사용할 수 없습니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  개체에 로컬 오버 로드 된 연산자를 확인 합니다.  
  
2.  적절 한 단항 연산자를 오버 로드를 선택 합니다.