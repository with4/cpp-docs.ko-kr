---
title: 심각한 오류 C1126 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1126
dev_langs:
- C++
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a3ff02d69679074186e593d5e1c16bdf56d1052
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1126"></a>심각한 오류 C1126
'identifier': 자동 할당 크기를 초과 합니다.  
  
 함수 (및 제한 된 양의 스왑 가능 함수에 대 한 추가 20 바이트 같은 컴파일러에 사용 된 공간)의 지역 변수에 할당 된 공간 한계를 초과 합니다.  
  
 이 오류를 해결 하려면 사용 `malloc` 또는 `new` 많은 양의 데이터를 할당할 수 있습니다.