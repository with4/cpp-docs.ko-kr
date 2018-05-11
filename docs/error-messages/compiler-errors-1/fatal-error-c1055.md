---
title: 심각한 오류 C1055 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1055
dev_langs:
- C++
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07f0dc0e8dca08e8b0de47b73516d3fdfa21435b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1055"></a>심각한 오류 C1055
컴파일러 한계: 키가 부족  
  
 소스 파일에 너무 많은 기호가 있습니다. 컴파일러는 기호 테이블에 대 한 해시 키 부족합니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  소스 파일을 더 작은 파일로 분할 합니다.  
  
2.  불필요 한 헤더 파일을 제거 합니다.  
  
3.  새 계정을 만드는 대신 임시 및 전역 변수를 다시 사용 합니다.