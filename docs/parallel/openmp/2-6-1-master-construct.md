---
title: 2.6.1 master 구문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a60a8df380fdcc0052d8fe2d070c8d926bcb28f8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689558"
---
# <a name="261-master-construct"></a>2.6.1 master 구문
**마스터** 지시문 팀의 마스터 스레드에 의해 실행 되는 구조화 된 블록을 지정 하는 구조를 식별 합니다. 구문은 **마스터** 지시문은 다음과 같습니다.  
  
```  
#pragma omp master new-linestructured-block  
```  
  
 팀의 다른 스레드를 연결된 하는 구조화 된 블록을 실행 하지 마십시오. 항목을 또는 종료를 master 구문 중 하나에 없는 묵시적된 장벽이 있습니다.