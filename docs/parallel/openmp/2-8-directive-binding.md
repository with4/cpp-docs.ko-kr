---
title: 2.8 지시문 바인딩 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02492b228b4bb47a800955f078a59ce680312a87
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="28-directive-binding"></a>2.8 지시문 바인딩
동적 바인딩 지시문의 다음 규칙을 따라야 합니다.  
  
-   **에 대 한**, **섹션**, **단일**, **마스터**, 및 **장벽** 지시문에 바인딩하는 동적으로 바깥쪽 **병렬**모든 값에 관계 없이, 있는 경우 **경우** 해당 지시문에 있을 수 있는 절. 병렬 영역 없는 현재 실행 중인 경우 지시문은 마스터 스레드에 이루어진 팀에서 실행 됩니다.  
  
-   **정렬** 지시문에 바인딩한 동적으로 바깥쪽 **에 대 한**합니다.  
  
-   **원자성** 지시문은와 관련 하 여 단독 액세스를 적용 **원자성** 모든 스레드 뿐 아니라 현재 팀의에서 지시문입니다.  
  
-   **중요** 지시문은와 관련 하 여 단독 액세스를 적용 **중요** 모든 스레드 뿐 아니라 현재 팀의에서 지시문입니다.  
  
-   지시문 되지 바인딩할 수는 가장 가까운 바깥쪽 모든 지시문에 동적으로 묶는 **병렬**합니다.