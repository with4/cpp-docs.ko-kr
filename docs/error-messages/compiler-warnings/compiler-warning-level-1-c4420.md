---
title: 컴파일러 경고 (수준 1) C4420 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4420
dev_langs:
- C++
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98336a30e7174b62df48e93a04ba9ee7ddcc919a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279112"
---
# <a name="compiler-warning-level-1-c4420"></a>컴파일러 경고(수준 1) C4420
'operator': 'operator'를 대신 사용 하 여 연산자를 사용할 수 없음 런타임 검사가 손상 될 수 있습니다.  
  
 사용 하는 경우이 경고는 발생는 [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (새/삭제 확인 벡터) 벡터 양식이 없는 찾을 수 있습니다. 이 경우 비 벡터 형식은 사용 됩니다.  
  
 /Rtcv가 제대로 작동 하려면에서 컴파일러는 항상 호출의 벡터 형식은 [새](../../cpp/new-operator-cpp.md)/[삭제](../../cpp/delete-operator-cpp.md) 벡터 구문을 사용한 경우입니다.