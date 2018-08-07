---
title: 3.3 타이밍 루틴 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 21060d64-cbe8-4e38-8718-3a68d6a57be3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3b8fc16e34124419362d5989131c2cf66df30b6
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694913"
---
# <a name="33-timing-routines"></a>3.3 타이밍 루틴
이 섹션에서 설명 하는 함수는 휴대용 벽 시계 타이머를 지원 합니다.  
  
-   `omp_get_wtime` 함수 경과 된 벽 시계 시간을 반환 합니다.  
  
-   `omp_get_wtick` 함수 연속 클록 틱 간 시간 (초)을 반환 합니다.